# Fundamentos Java – Resumo para Estudo

## 1. Tipos Primitivos vs Objetos (Wrappers)

### Tipos Primitivos
- Guardam o valor diretamente na memória
- Não possuem métodos
- Não aceitam `null`
- Melhor performance

Exemplos:
```java
int idade = 27;
double salario = 3500.50;
boolean ativo = true;
char sexo = 'F';
```

Principais tipos primitivos:
- int 
- double 
- boolean 
- char 
- long
- float 
- short 
- byte

### Objetos (Wrappers)
São classes que representam os tipos primitivos  
Possuem métodos   
Podem ser null   
Necessários para coleções (List, Map)

```java
Integer idade = 27;
Double salario = 3500.50;
Boolean ativo = true;
Character sexo = 'F';
```

Equivalências   
int -> Integer   
double -> Double   
boolean -> Boolean   
char -> Character

### Principais Métodos de Integer
- parseInt (String s): converte String para int.
```java
int valor = Integer.parseInt("42");
```
-valueOf(String s): converte String para Integer (objeto).
```java
Integer valor = Interger.valueOf("42")
```
- compareTo(Integer outro): compara dois Integer. Retorna um int. 
- 0 = os valores são iguais
- menor que 0 = o objeto que chamou o método é menor
- maior que 0 = o objeto que chamou o método é maior

```java
Integer a = 10;
Integer b = 20;

a.compareTo(b); //-1 (10 < 20)
b.compareTo(a); //1 (20 > 10)
a.compareTo(10); //0 (pois são iguais)
```
📌 O número exato (-1, 1, -10, etc.) não importa   
o que importa é se é negativo, zero ou positivo

- equals(Object o): compara valor, não referência;
```java
Integer a = 100;
Integer b = 100;

a.equals(b); //true
```
- esse método evita erros comuns do ==.
- intValue(): (converte Integer para int)
```java
Integer numero = 50;
int n = numero.intValue();
```
- Métodos utilitários estáticos:
```java
Integer.max(int a, int b)
Integer.min(int a, int b)
Integer.sum(int a, int b)
```
👉 Sempre recebem dois valores   
👉 Sempre retornam um único valor

### Principais Métodos da classe Double
- parseDouble (String s): converte String para double.
```java
double valor = Double.parseDouble("471.165");
```
- valueOf(String s): converte String para Double (objeto)
```java
Double valor = Double.valueOf("10.5")
```
- compareTo(Double outro): compara dois Double.
```java
Double a = 2.5;
Double b = 3.0;

a.compareTo(b);
```
é mais seguro que > ou < quando se trabalha com objetos.
- equals (Object o): compara valores.
```java
Double a = 2.0;
Double b = 2.0;

a.equals(b); //true
```
- doubleValue(): converte Double para double.

```java
Double valor = 9.8;
double v = valor.doubleValue();
```
Métodos utilitários estáticos

```java
Double.max(2.5, 3.5); // 3.5
Double.min(2.5, 3.5); // 2.5
Double.sum(1.2, 2.3); // 3.5
```
