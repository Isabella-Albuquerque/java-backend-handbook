# Casting

## Conceito
É a conversão explícita ou implícita de um tipo para outro. Ocorre quando é necessário tratar um valor de terminado tipo como se fosse de outro.

## Casting Implícito - widening
Acontece automaticamente quando o tipo de destino é maior que o de origem
—> sem risco de perda de dados

```java
byte b = 10;
short s = b;   // byte → short  
int i = s;     // short → int   
long l = i;    // int → long    
float f = l;   // long → float  
double d = f;  // float → double 
```

Hierarquia do menor para o maior: ``byte → short → int → long → float → double``

## Casting explícito - Narrowing
Necessário quando o tipo de destino é menor
—> existe o risco de perda de dados

```java
double preco = 9.99;
int truncado = (int) preco; //  resultado: 9 — decimal perdido

long populacao = 8_000_000_000L;
int valor = (int) populacao; // ⚠️ resultado imprevisível — estoura o limite do int
```

## Casting entre primitivos e Strings
Primitivos não fazem cast direto para String, para isso é necessário usar métodos:

``` java
// Primitivo → String
int numero = 42;
String s1 = String.valueOf(numero);    // ✅ recomendado
String s2 = Integer.toString(numero);  // ✅ alternativa
String s3 = "" + numero;              // ⚠️ funciona, mas evite

// String → primitivo
String texto = "42";
int i = Integer.parseInt(texto);       // ✅
double d = Double.parseDouble("3.14"); // ✅
```

## Cuidados

**Perda Silenciosa de dados**
```java
int valor = 130;
byte b = (byte) valor; // resultado: -126 pois estoura o limite do byte (-128 a 127)

```

**Tipos Incompatíveis**
````java
String texto = (String) new Integer(42); // ❌ não compila pois tipos não têm relação de herança
````