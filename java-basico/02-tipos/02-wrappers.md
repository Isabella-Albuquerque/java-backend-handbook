# Wrappers

## Conceito
São classes que empacotam os tipos primitivos.
- transformam um valor simples em um objeto, adicionando métodos e comportamentos.
- Podem assumir valor null.

## Autoboxing e Unboxing
Java converte primitivo ↔ wrapper automaticamente.

```java
// Autoboxing — primitivo vira wrapper automaticamente
Integer a = 10;  // Java faz: Integer.valueOf(10)

// Unboxing — wrapper vira primitivo automaticamente
int b = a;       // Java faz: a.intValue()
```

## Principais Wrappers

### Integer
é o mais utilizado entre os numéricos inteiros. Além de embalar o int, entrega conversões e constantes essenciais:

````java
Integer.parseInt("42");       // String → int
Integer.valueOf(42);          // int → Integer
Integer.MAX_VALUE;            // 2.147.483.647
Integer.MIN_VALUE;            // -2.147.483.648
Integer.toBinaryString(10);   // "1010"
Integer.compare(a, b);        // compara dois inteiros
````


### Double
cobre os casos de números decimais e traz verificações importantes para operações matemáticas.

````java
Double.parseDouble("3.14");   // String → double
Double.isNaN(0.0 / 0.0);     // verifica Not a Number → true
Double.isInfinite(1.0 / 0.0); // verifica infinito → true
Double.MAX_VALUE;             // maior double possível
````

### Boolean
útil na conversão de texto para lógica: qualquer valor diferente de "true" (ignorando maiúsculas) retorna false.
```java
Boolean.parseBoolean("true");  // → true
Boolean.parseBoolean("TRUE");  // → true
Boolean.parseBoolean("sim");   // → false
Boolean.toString(true);        // → "true"
```
### String

```java
String.valueOf(42);        // int → String
String.valueOf(3.14);      // double → String
String.valueOf(true);      // boolean → String
Integer.toString(42);      // alternativa direta
```