
# Programação Orientada a Objetos

## Conceito
É um paradigma de programação que organiza o software em **objetos que representam conceitos do domínio**, combinando **estado (dados)** e **comportamento (regras e ações)** em uma única unidade coesa.  
O objetivo é facilitar a modelagem do problema, reduzir acoplamento, aumentar manutenibilidade e permitir a evolução do sistema ao longo do tempo.

Possui **4 pilares fundamentais**:
- Abstração  
- Encapsulamento  
- Herança  
- Polimorfismo  

---

## Objetos e Instâncias  

### Classe
Uma classe define:
- Quais dados um objeto possui (atributos)
- Quais operações ele pode executar (métodos)
- Quais regras governam esse comportamento  

Ela funciona como um **contrato** e uma **definição de tipo**, não como algo concreto em execução.

### Instância
Uma instância é um **objeto criado a partir de uma classe**, que segue sua estrutura e comportamento, mas **existe de forma independente**, com **estado e identidade próprios**.  
É a **materialização concreta da classe na memória**, criada em tempo de execução pela JVM.

```java
public class User {
    private String id;
    private String email;
    private boolean active;
    
    public User(String id, String email) {
        this.id = Objects.requireNonNull(id);
        this.email = Objects.requireNonNull(email);
        this.active = true;
    }
    
    public String getId() {
        return id;
    }
    
    public boolean isActive() {
        return active;
    }
}
````

Cada vez que `new User(...)` é chamado, uma **nova instância** é criada, com identidade própria, mesmo que os valores sejam iguais.

### Boas Práticas

* [x] Objetos encapsulam comportamento, não apenas dados.
* [x] Preferir objetos imutáveis quando possível.
* [x] Criar instâncias válidas desde o construtor.
* [x] Evitar `new` espalhado → usar fábricas ou injeção de dependência (DI).

---

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

## Uso do `this`

A palavra-chave `this` é uma **referência para a instância atual do objeto**.
Ela permite acessar atributos e métodos do próprio objeto de forma explícita.

### Usos comuns

* Diferenciar atributos de variáveis locais.
* Passar o próprio objeto como argumento na chamada de um método ou construtor.

O uso correto do `this` melhora a legibilidade, evita ambiguidades e torna o código mais claro, especialmente em construtores e métodos que recebem parâmetros com o mesmo nome dos atributos.

```java
public class Product {
    private String name;
    private double price;

    public Product(String name, double price) {
        // "this" referencia o atributo da instância
        this.name = name;
        this.price = price;
    }

    public void updatePrice(double price) {
        // diferencia o atributo da variável local
        this.price = price;
    }
}

```
No exemplo acima, this é uma referência à instância atual do objeto.

Ele é usado para:

Diferenciar atributos da classe de parâmetros ou variáveis locais com o mesmo nome.

Tornar explícito que estamos acessando o estado do próprio objeto.
Sem this, o código ficaria ambíguo, porque name = name e price = price se refeririam apenas aos parâmetros, não aos atributos da classe.


## Encapsulamento
É um princípio que consiste em esconder detalhes de implementação de uma classe, expondo apenas operações seguras e que mantenham os objetos em um estado consistente.

Encapsulamento = controlar acesso ao estado interno.

O objeto decide como e quando seu estado pode mudar.

É base para baixo acoplamento.

Regra Geral Basica:
- um objeto *não* deve expor nenhum atributo(usar modificador de acesso private)


### Erros comuns
Expor campos como public.

Getter e setter para tudo, sem regra.

Permitir estado inválido temporário.

Validar fora do objeto (em controller/service).

### Boas práticas
Campos sempre private.

Métodos expressam intenções, não operações genéricas.

Preferir métodos como activate(), cancel(), close() em vez de setters.

Invariantes protegidas internamente.

### Impacto arquitetural
Encapsulamento forte → domínio mais estável.

Menos efeitos colaterais.

Testes focam em comportamento, não implementação.

```java
private String name;

public Strin getName(){
    return name;
}

public void setName(String name){
    this.name = name:
}
```
```
```
