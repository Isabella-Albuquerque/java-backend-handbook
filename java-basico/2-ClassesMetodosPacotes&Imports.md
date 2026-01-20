# Classes, Métodos, Pacotes e Imports em Java

## 1. Classes

Uma **classe** é um modelo ou projeto para criar objetos. Ela define um tipo de dado, encapsulando dados (atributos) e comportamentos (métodos) que os objetos daquela classe terão.

**Exemplo:**

```java
// Definição da classe Carro
public class Carro {
    // Atributos (estado do objeto)
    String modelo;
    String cor;
    int ano;

    // Comportamentos (métodos)
    public void acelerar() {
        System.out.println("O carro está acelerando!");
    }

    public void frear() {
        System.out.println("O carro está freando.");
    }
}
```

Neste exemplo, `Carro` é uma classe com três atributos (`modelo`, `cor`, `ano`) e dois métodos (`acelerar`, `frear`).

## 2. Métodos

Um **método** é um bloco de código que realiza uma tarefa específica. Métodos são definidos dentro de uma classe e descrevem os comportamentos dos objetos daquela classe.

**Estrutura de um método:**

```java
<modificador_de_acesso> <tipo_de_retorno> <nome_do_metodo>(<parametros>) {
    // Corpo do método
    return <valor_de_retorno>;
}
```

- **Modificador de acesso:** Define a visibilidade do método (ex: `public`, `private`).
- **Tipo de retorno:** O tipo de dado que o método retorna. Use `void` se o método não retornar nada.
- **Nome do método:** Um nome descritivo para a ação que o método realiza.
- **Parâmetros:** Variáveis que o método recebe como entrada (opcional).

**Exemplo:**

```java
public class Calculadora {
    // Método que soma dois números e retorna o resultado
    public int somar(int a, int b) {
        return a + b;
    }

    // Método que não retorna valor (void)
    public void imprimirMensagem(String mensagem) {
        System.out.println(mensagem);
    }
}
```

## 3. Construtores, Getters e Setters

### Construtores

Um **construtor** é um método especial usado para inicializar um objeto recém-criado. Ele é chamado no momento da criação do objeto (usando a palavra-chave `new`). O construtor tem o mesmo nome da classe e não possui tipo de retorno.

- **Função:** Garantir que o objeto seja criado em um estado válido, com seus atributos essenciais inicializados.

```java
public class Pessoa {
    private String nome;
    private int idade;

    // Construtor da classe Pessoa
    public Pessoa(String nomeInicial, int idadeInicial) {
        this.nome = nomeInicial;
        this.idade = idadeInicial;
    }
}

// Como usar o construtor para criar um objeto
Pessoa pessoa1 = new Pessoa("Maria", 25);
```

### Getters e Setters

Getters e setters são métodos usados para ler e modificar os valores de atributos privados de uma classe, respectivamente. Isso é fundamental para o **encapsulamento**, um dos pilares da Programação Orientada a Objetos.

- **Atributos `private`:** Ao declarar os atributos como `private`, você impede o acesso direto a eles de fora da classe.
- **Getters (Acessores):** Métodos públicos que retornam o valor de um atributo privado. Por convenção, começam com `get` seguido do nome do atributo (ex: `getNome`).
- **Setters (Modificadores):** Métodos públicos que alteram o valor de um atributo privado. Por convenção, começam com `set` seguido do nome do atributo (ex: `setNome`). Eles geralmente recebem um parâmetro com o novo valor e não retornam nada (`void`).

- **Função:** Controlar o acesso aos dados de um objeto. Você pode adicionar lógicas de validação dentro de um setter (por exemplo, não permitir uma idade negativa) ou formatar um dado antes de retorná-lo em um getter.

**Exemplo:**

```java
public class Conta {
    private double saldo;

    // Getter para o saldo
    public double getSaldo() {
        return this.saldo;
    }

    // Setter para o saldo com validação
    public void setSaldo(double novoSaldo) {
        if (novoSaldo >= 0) {
            this.saldo = novoSaldo;
        } else {
            System.out.println("Não é possível definir um saldo negativo.");
        }
    }
} 
```

## 4. Pacotes (Packages)

**Pacotes** são usados para organizar classes relacionadas em um namespace. Eles ajudam a evitar conflitos de nomes e a estruturar projetos grandes. A convenção é usar o nome de domínio invertido da sua empresa para garantir que os pacotes sejam únicos.

**Exemplo:**

Se o domínio da sua empresa é `minhaempresa.com`, seus pacotes poderiam começar com `com.minhaempresa`.

Para declarar que uma classe pertence a um pacote, use a palavra-chave `package` no início do arquivo.

```java
// O arquivo Carro.java está no pacote com.minhaempresa.veiculos
package com.minhaempresa.veiculos;

public class Carro {
    // ...
}
```

A estrutura de diretórios do seu projeto deve corresponder à estrutura de pacotes. Para o exemplo acima, o arquivo `Carro.java` estaria em: `src/main/java/com/minhaempresa/veiculos/Carro.java`.

## 5. Imports

A declaração `import` permite que você use classes de outros pacotes no seu código sem precisar escrever o nome completo do pacote toda vez.

**Exemplo:**

Imagine que você tem uma classe `Oficina` no pacote `com.minhaempresa.servicos` e quer usar a classe `Carro` do pacote `com.minhaempresa.veiculos`.

```java
package com.minhaempresa.servicos;

// Importando a classe Carro para poder usá-la diretamente
import com.minhaempresa.veiculos.Carro;

public class Oficina {
    public void consertarCarro() {
        // Criando um objeto (instância) da classe Carro
        Carro meuCarro = new Carro();
        meuCarro.modelo = "Fusca";
        
        System.out.println("Consertando o carro modelo: " + meuCarro.modelo);
    }
}
```

- **`import com.minhaempresa.veiculos.Carro;`**: Importa apenas a classe `Carro`.
- **`import com.minhaempresa.veiculos.*;`**: Importa todas as classes públicas do pacote `veiculos`. É uma boa prática importar apenas as classes que você realmente precisa.

Classes do pacote `java.lang` (como `String` e `System`) são importadas automaticamente em todos os arquivos Java.

