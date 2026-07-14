# For

## Conceito
O laço for é uma estrutura de repetição usada quando você sabe quantas vezes um bloco de código deve ser executado ou quando deseja percorrer uma sequência de elementos.

## Sintaxe

```java
for (inicialização; condição; atualização) {
    // código a ser repetido
}
```
Exemplo pratico
````java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
````

Nesse exemplo:

- int i = 1 → inicializa a variável de controle;
- i <= 5 → define enquanto o laço continuará executando;
- i++ → incrementa a variável ao final de cada repetição.

## Aplicacoes
Usado para percorrer arrays, listas ou executar uma acao um numero determinado de vezes.

## Pontos de Atencao

- Loops infinitos: A condição nunca se torna falsa.
- Erro de limite (off-by-one): a primeira contagem é do ZERO, isso significa que uma condicao definida como <= 5 executa 6 vezes.
- Acessar posições inválidas de um array ou lista: código lança ArrayIndexOutOfBoundsException