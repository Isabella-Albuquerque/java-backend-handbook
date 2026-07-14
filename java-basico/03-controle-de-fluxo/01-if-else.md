# If / Else

## Conceito

É a estrutura de decisão mais básica do Java. Ela executa um bloco de código se uma condição for **verdadeira** e outro bloco (opcional) se for **falsa**.

---

## Aplicacoes

### Apenas If

Executa somente se a condição for verdadeira.

```java
int idade = 20;

if (idade >= 18) {
    System.out.println("Maior de idade");
}
```

### if / else

Executa um caminho ou outro.

```java
int idade = 20;

if (idade >= 18) {
    System.out.println("Maior de idade");
} else {
    System.out.println("Menor de idade");
}
```

### if / else if / else

Permite testar múltiplas condições.

```java
int nota = 75;

if (nota >= 90) {
    System.out.println("A");
} else if (nota >= 80) {
    System.out.println("B");
} else if (nota >= 70) {
    System.out.println("C");
} else {
    System.out.println("Reprovado");
}
```

---

## Observacoes

a condicao testada deve sempre produzir um boolean como resultado.

### ✅ Expressões válidas

```java
if (ativo == true) { }

if (ativo) { }          // mais limpo — boolean direto

if (saldo > 0) { }

if (nome != null && !nome.isEmpty()) { }
```

### ❌ Expressões inválidas

```java
if (1) { }              // int não é boolean

if (x = 10) { }         // atribuição, não comparação
```


---

## Operador Ternário

Para atribuições simples, o operador ternário costuma ser mais conciso.

### `if / else`

```java
String status;

if (ativo) {
    status = "Ativo";
} else {
    status = "Inativo";
}
```

### Operador ternário

```java
String status = ativo ? "Ativo" : "Inativo";
```

> Utilize o operador ternário apenas para expressões simples. Para lógica com múltiplas instruções, prefira `if / else`.


---

##  Early Return

Evite níveis excessivos de aninhamento.

Exemplo:
```java
public void processar(Usuario u) {
    if (u != null) {
        if (u.isAtivo()) {
            if (u.temSaldo()) {
                // lógica principal
            }
        }
    }
}
```

#### Utilizando Early Return:

```java
public void processar(Usuario u) {
    if (u == null) return;
    if (!u.isAtivo()) return;
    if (!u.temSaldo()) return;

    // lógica principal
}
```

---