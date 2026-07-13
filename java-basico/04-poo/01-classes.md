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
