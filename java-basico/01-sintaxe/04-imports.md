# Imports

A declaração import permite usar classes de outros pacotes no código sem precisar escrever o nome completo do pacote toda vez.

## Tipos de Import

````java
// Import específico — recomendado 
import br.com.empresa.util.Formatador;

// Import por wildcard — traz todas as classes do pacote
import br.com.empresa.util.*;  // deve ser evitadp — dificulta rastrear de onde vem cada classe

// Import estático — traz métodos ou constantes estáticas diretamente
import static java.lang.Math.PI;
import static java.lang.Math.sqrt;

public class App {
    public static void main(String[] args) {
        System.out.println(PI);      // sem precisar escrever Math.PI
        System.out.println(sqrt(9)); // sem precisar escrever Math.sqrt(9)
    }
}
````

## Pacote Java.lang
O `java.lang` é o pacote fundamental da linguagem Java, que contém as classes sem as quais o Java não funcionaria como `String`, `Math`, `System`, `Object`, `Thread` e a base do sistema de erros.

- é o único importado automaticamente pela JVM em todo arquivo `.java`
- Um detalhe importante dentro dele é a classe `Object`, mãe de todas as classes Java. Toda classe que você cria herda dela automaticamente, ganhando métodos como `toString()`, `equals()` e `hashCode()` sem precisar declarar nada.