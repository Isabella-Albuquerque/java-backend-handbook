
## Construtores

São os métodos responsáveis por **inicializar o objeto após ele já ter sido criado pela JVM**.
Eles garantem que a instância comece sua vida em um **estado válido e consistente**.

### Usos comuns

* Inicializar valores dos atributos do objeto.
* Permitir ou obrigar que o objeto receba dados e/ou dependências no momento em que é instanciado.

```java
User user = new User("isa@email.com");
```

### O que ocorre internamente

* A JVM aloca memória para o objeto `User`.
* O objeto passa a existir (ainda com valores default).
* O construtor é chamado.
* O construtor inicializa o estado do objeto.

### Construtor default

Em Java, se nenhum construtor customizado for especificado, o compilador gera um **construtor default**.
Ele:

* Não recebe parâmetros
* Não executa lógica adicional
* Chama implicitamente `super()`

```java
public class User {
}

User user = new User();
```

Nesse caso, os campos são inicializados com valores default:

* `0` para números
* `false` para boolean
* `null` para referências

### Construtor personalizado

Um construtor personalizado deve:

* Ter o mesmo nome da classe
* Possuir parênteses com parâmetros (ou vazios)
* Ter um modificador de acesso (geralmente `public`)

```java
public class Order {
    private final UUID id;
    private final Instant createdAt;
    private OrderStatus status;

    public Order(UUID id) {
        this.id = Objects.requireNonNull(id);
        this.createdAt = Instant.now();
        this.status = OrderStatus.CREATED;
    }
}
```

Aqui, o construtor garante que o objeto:

* Nunca exista sem `id`
* Sempre tenha uma data de criação
* Comece em um estado válido

### Boas Práticas

* Poucos parâmetros e semanticamente claros.
* Validar tudo que for obrigatório no construtor.
* Usar *factory methods* quando o construtor ficar complexo.

---