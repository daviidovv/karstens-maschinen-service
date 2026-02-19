# Code Standards

Letzte Aktualisierung: 2026-02-19

## Java/Spring Boot

### Allgemein

- Java 21 Features nutzen (Records, Pattern Matching, etc.)
- Alle Klassen in `de.karstensmaschinen.service` Package
- Eine Klasse pro Datei
- Max. 500 Zeilen pro Klasse
- Max. 50 Zeilen pro Methode

### Dependency Injection

```java
// RICHTIG: Constructor Injection
@Service
public class ProductService {
    private final ProductRepository productRepository;

    public ProductService(ProductRepository productRepository) {
        this.productRepository = productRepository;
    }
}

// FALSCH: Field Injection
@Service
public class ProductService {
    @Autowired  // VERBOTEN!
    private ProductRepository productRepository;
}
```

### Transactions

```java
@Service
@Transactional(readOnly = true)  // Default: read-only
public class ProductService {

    public Product findById(UUID id) {
        // read-only, kein zusätzliches @Transactional nötig
    }

    @Transactional  // Überschreibt read-only für schreibende Methoden
    public Product create(CreateProductRequest request) {
        // schreibend
    }
}
```

### DTOs

```java
// Request DTO
public record CreateProductRequest(
    @NotBlank String name,
    @NotBlank String description,
    @NotNull UUID categoryId
) {}

// Response DTO
public record ProductResponse(
    UUID id,
    String name,
    String description,
    String categoryName,
    LocalDateTime createdAt
) {}
```

### Entity

```java
@Entity
@Table(name = "product")
@Data
@NoArgsConstructor
@AllArgsConstructor
@Builder
public class Product {

    @Id
    @GeneratedValue(strategy = GenerationType.UUID)
    private UUID id;

    @Column(nullable = false)
    private String name;

    @Column(columnDefinition = "TEXT")
    private String description;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "category_id")
    private Category category;

    @CreatedDate
    @Column(name = "created_at", nullable = false, updatable = false)
    private LocalDateTime createdAt;

    @LastModifiedDate
    @Column(name = "updated_at", nullable = false)
    private LocalDateTime updatedAt;
}
```

### Controller

```java
@RestController
@RequestMapping("/api/v1/products")
@Validated
public class ProductController {

    private final ProductService productService;

    public ProductController(ProductService productService) {
        this.productService = productService;
    }

    @GetMapping
    public ResponseEntity<List<ProductResponse>> findAll() {
        return ResponseEntity.ok(productService.findAll());
    }

    @PostMapping
    public ResponseEntity<ProductResponse> create(
            @Valid @RequestBody CreateProductRequest request) {
        ProductResponse response = productService.create(request);
        return ResponseEntity.status(HttpStatus.CREATED).body(response);
    }
}
```

## Naming Conventions

### Klassen
| Typ | Konvention | Beispiel |
|-----|------------|----------|
| Controller | `*Controller` | `ProductController` |
| Service | `*Service` | `ProductService` |
| Repository | `*Repository` | `ProductRepository` |
| Entity | Kein Suffix | `Product` |
| Request DTO | `*Request` | `CreateProductRequest` |
| Response DTO | `*Response` | `ProductResponse` |
| Mapper | `*Mapper` | `ProductMapper` |
| Exception | `*Exception` | `ProductNotFoundException` |

### Methoden
| Operation | Prefix | Beispiel |
|-----------|--------|----------|
| Erstellen | `create` | `createProduct()` |
| Lesen (einzeln) | `get` / `findById` | `getProduct()` |
| Lesen (alle) | `findAll` | `findAllProducts()` |
| Aktualisieren | `update` | `updateProduct()` |
| Löschen | `delete` | `deleteProduct()` |
| Boolean | `is` / `has` / `can` | `isActive()` |

## Tests

### Naming

```java
@Test
void methodName_scenario_expectedBehavior() {
    // Beispiele:
    // findById_existingProduct_returnsProduct
    // create_invalidName_throwsValidationException
    // delete_nonExistingProduct_throwsNotFoundException
}
```

### Struktur (AAA)

```java
@Test
void findById_existingProduct_returnsProduct() {
    // Arrange
    UUID productId = UUID.randomUUID();
    Product product = createTestProduct(productId);
    when(productRepository.findById(productId)).thenReturn(Optional.of(product));

    // Act
    ProductResponse result = productService.findById(productId);

    // Assert
    assertThat(result.id()).isEqualTo(productId);
    assertThat(result.name()).isEqualTo(product.getName());
}
```

## Git Commits

### Format

```
<type>: <kurze Beschreibung>

[optionaler Body mit mehr Details]

[optionaler Footer]
```

### Types
- `feat`: Neues Feature
- `fix`: Bugfix
- `docs`: Dokumentation
- `refactor`: Code-Refactoring
- `test`: Tests
- `chore`: Sonstiges (Build, Dependencies)

### Beispiele

```
feat: Add product search endpoint

fix: Fix null pointer in category lookup

docs: Update API documentation for inquiries
```
