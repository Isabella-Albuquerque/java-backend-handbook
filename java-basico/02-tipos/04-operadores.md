# Operadores

## Conceito
Operadores são símbolos que instruem a JVM a executar uma operação sobre um ou mais valores. Esses valores são chamados de operandos, e o resultado sempre produz um novo valor.

## 1. Aritméticos
realizam cálculos matemáticos entre valores numéricos.

```java
int a = 10, b = 3;

a + b;  // 13 — soma
a - b;  // 7  — subtração
a * b;  // 30 — multiplicação
a / b;  // 3  — divisão inteira (descarta o decimal)
a % b;  // 1  — módulo (resto da divisão)
```

> `10 / 3` retorna `3`, não `3.33` — divisão entre inteiros sempre resulta em inteiro. Para obter decimal, um dos operandos precisa ser `double`:
> ```java
> 10.0 / 3  // 3.3333...
> ```

---

## 2. Atribuição

Armazenam ou atualizam o valor de uma variável.

```java
int x = 10;

x += 5;  // x = x + 5  → 15
x -= 3;  // x = x - 3  → 12
x *= 2;  // x = x * 2  → 24
x /= 4;  // x = x / 4  → 6
x %= 4;  // x = x % 4  → 2
```

---

## 3. Incremento e Decremento

Adicionam ou subtraem 1 de uma variável de forma compacta.

```java
int x = 5;

x++;  // pós-incremento — usa o valor, depois incrementa
++x;  // pré-incremento — incrementa, depois usa o valor
x--;  // pós-decremento
--x;  // pré-decremento
```

A diferença importa quando usado dentro de uma expressão:

```java
int x = 5;
int a = x++;  // a = 5, x = 6 — atribuiu antes de incrementar
int b = ++x;  // b = 7, x = 7 — incrementou antes de atribuir
```

---

## 4. Relacionais

Comparam dois valores e sempre retornam true ou false.

```java
int a = 10, b = 20;

a == b;  // false — igual
a != b;  // true  — diferente
a > b;   // false — maior
a < b;   // true  — menor
a >= b;  // false — maior ou igual
a <= b;  // true  — menor ou igual
```

> Nunca use `==` para comparar objetos como `String` — use `.equals()`:
> ```java
> "Java".equals(outraString); // ✅
> "Java" == outraString;      // ❌ compara referência, não conteúdo
> ```

---

## 5. Lógicos

Combinam condições booleanas para formar expressões de decisão.

```java
boolean a = true, b = false;

a && b;  // false — AND — ambos precisam ser true
a || b;  // true  — OR  — basta um ser true
!a;      // false — NOT — inverte o valor
```

**Short-circuit** — Java para de avaliar assim que o resultado é certo:

```java
// Se a primeira condição for false, a segunda nem é avaliada
if (usuario != null && usuario.isAtivo()) { }

// Se a primeira for true, a segunda nem é avaliada
if (modoDebug || validar()) { }
```

---

## 6. Ternário

Versão compacta do `if/else` para atribuições simples:

```java
int idade = 20;
String resultado = idade >= 18 ? "maior de idade" : "menor de idade";

// Equivale a:
String resultado;
if (idade >= 18) {
    resultado = "maior de idade";
} else {
    resultado = "menor de idade";
}
```

> Use o ternário apenas para expressões simples — para lógica complexa, prefira o `if/else` por legibilidade.

---

## 7. Bitwise — bit a bit

Manipulam os bits individuais de um valor numérico diretamente na memória.

```java
int a = 0b1010; // 10
int b = 0b1100; // 12

a & b;   // 0b1000 = 8  — AND bit a bit
a | b;   // 0b1110 = 14 — OR bit a bit
a ^ b;   // 0b0110 = 6  — XOR bit a bit
~a;      // inverte todos os bits
a << 1;  // 0b10100 = 20 — desloca bits à esquerda (multiplica por 2)
a >> 1;  // 0b0101  = 5  — desloca bits à direita (divide por 2)
```