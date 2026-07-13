
# Uso do `this`

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
