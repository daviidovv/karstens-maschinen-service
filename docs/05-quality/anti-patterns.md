# Anti-Patterns

Diese Patterns sind VERBOTEN im Projekt.

## Backend (Java/Spring Boot)

### Field Injection

```java
// FALSCH
@Service
public class ProductService {
    @Autowired
    private ProductRepository repo;  // VERBOTEN!
}

// RICHTIG
@Service
public class ProductService {
    private final ProductRepository repo;

    public ProductService(ProductRepository repo) {
        this.repo = repo;
    }
}
```

### Entity als API-Response

```java
// FALSCH
@GetMapping("/{id}")
public Product getProduct(@PathVariable UUID id) {
    return productRepository.findById(id).orElseThrow();  // VERBOTEN!
}

// RICHTIG
@GetMapping("/{id}")
public ProductResponse getProduct(@PathVariable UUID id) {
    return productService.findById(id);  // Service gibt DTO zurück
}
```

### Business-Logik im Controller

```java
// FALSCH
@PostMapping
public ResponseEntity<?> create(@RequestBody CreateProductRequest request) {
    // VERBOTEN: Business-Logik im Controller
    if (categoryRepository.findById(request.categoryId()).isEmpty()) {
        throw new CategoryNotFoundException();
    }
    Product product = new Product();
    product.setName(request.name());
    // ...
}

// RICHTIG
@PostMapping
public ResponseEntity<ProductResponse> create(@RequestBody CreateProductRequest request) {
    return ResponseEntity.status(HttpStatus.CREATED)
        .body(productService.create(request));  // Business-Logik im Service
}
```

### God Class

```java
// FALSCH: Eine riesige Klasse für alles
public class ProductManager {
    // 1000+ Zeilen
    // Macht Validierung, Persistenz, Email, PDF, ...
}

// RICHTIG: Separation of Concerns
public class ProductService { /* Kernlogik */ }
public class ProductValidator { /* Validierung */ }
public class ProductEmailService { /* Email */ }
```

### Hardcoded Credentials

```java
// FALSCH
private static final String DB_PASSWORD = "geheim123";  // VERBOTEN!

// RICHTIG
@Value("${db.password}")
private String dbPassword;
```

### @Transactional im Controller

```java
// FALSCH
@RestController
public class ProductController {
    @Transactional  // VERBOTEN!
    @PostMapping
    public void create(...) { }
}

// RICHTIG
@Service
@Transactional(readOnly = true)
public class ProductService {
    @Transactional
    public void create(...) { }
}
```

## Frontend (React/TypeScript)

### Any-Type überall

```typescript
// FALSCH
const handleData = (data: any) => {  // VERBOTEN!
    console.log(data.something);
};

// RICHTIG
interface ProductData {
    id: string;
    name: string;
}

const handleData = (data: ProductData) => {
    console.log(data.name);
};
```

### Direct Fetch

```typescript
// FALSCH
useEffect(() => {
    fetch('/api/products')  // VERBOTEN!
        .then(res => res.json())
        .then(setProducts);
}, []);

// RICHTIG
const { data: products, isLoading } = useQuery({
    queryKey: ['products'],
    queryFn: () => api.getProducts()
});
```

### Class Components

```tsx
// FALSCH
class ProductList extends React.Component {  // VERBOTEN!
    render() { return <div>...</div>; }
}

// RICHTIG
const ProductList: React.FC = () => {
    return <div>...</div>;
};
```
