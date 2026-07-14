# Break e Continue

## Conceito

são comandos de controle de fluxo usados dentro de estruturas de repetição (for, while e do-while).

break interrompe imediatamente o laço.
continue interrompe apenas a iteração atual e passa para a próxima.

## Aplicacoes

- Break: utilizado para encerrar um laço antes que sua condição se torne falsa.

Exemplo: interromper a busca ao encontrar um elemento.
```java
for (int i = 0; i < numeros.length; i++) {
        if (numeros[i] == 10) {
        System.out.println("Encontrado!");
        break;
                }
                }
```

- Continue: utilizado para ignorar a iteração atual e continuar a próxima repetição do laço.

Exemplo: processar apenas números pares.

```java
for (int i = 1; i <= 10; i++) {
    if (i % 2 != 0) {
        continue;
    }

    System.out.println(i);
}
```

## Erros Comuns
- Utilizar break quando a intenção era apenas pular uma iteração (o correto seria continue).
- Utilizar continue quando era necessário encerrar completamente o laço (o correto seria break).
- Criar código de difícil leitura com muitos break e continue no mesmo laço.
- Esquecer que o break encerra apenas o laço atual, não todos os laços aninhados.
- Usar break ou continue em excesso em vez de reestruturar a lógica, tornando o código mais difícil de entender e manter.