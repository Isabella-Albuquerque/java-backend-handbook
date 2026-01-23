# Complexidade de Algoritmos

## O que é um algoritmo

Um algoritmo é uma sequência finita de passos bem definidos para resolver um problema. 
Exemplo: tarefa = encontrar um número em uma lista.  
1- Olhe o primeiro elemento  
2- Compare com o número buscado
3- Se for igual, pare  
4- Caso contrário, vá para o próximo  
5- Repita até acabar a lista

Isso é um algoritmo. Escrever em Java ou outra linguagem estamos codificando o algoritmo.  

## Características de um bom algoritmo

1- Correção: resolve o problema?
2- Eficiência: tempo e memória aceitáveis?
3- Legibilidade: outro dev entende?  
4- Escalabilidade: continua funcionando com maior volume de dados?

## Algoritmos Determinísticos VS Não Determinísticos
- **Determinístico** 
Dado um determinado conjunto de entradas, sempre produz o mesmo resultado, percorrendo exatamente os mesmos passos e estados em todas as execuções.

- **Não Determinísticos**
Mesmo com a mesma entrada, pode apresentar comportamentos, caminhos de execução ou resultados diferentes em execuções distintas.  
Exemplo: algoritmos probabilísticos, IA, heurísticas

## Iterativos VS Recursivos
- **Iterativos**
Usa loops (for, while). É mais seguro em produção devido ao menor risco de stack overflow
- **Recursivo**
A função chama a si mesma. 

**Busca Linear VS Busca Binária**  

LINEAR 

A busca linear percorre a lista elemento por elemento, do início ao fim, até encontrar o valor desejado ou terminar a lista.

```java
public static int buscaLinear(int[] arr, int alvo) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == alvo) {
            return i;
        }
    }
    return -1;
}
```
Nesse código, criamos a função buscaLinear, que retorna um inteiro representando o índice do elemento encontrado no array.
Ela recebe como parâmetros um array de inteiros (arr) e um valor inteiro (alvo), que é o elemento que desejamos buscar.

A função percorre o array do primeiro ao último elemento utilizando um laço for.
Em cada iteração, compara o valor armazenado na posição atual (arr[i]) com o valor alvo.
Se encontrar o elemento, retorna imediatamente o índice correspondente.

Caso o laço termine sem encontrar o valor, a função retorna -1, indicando que o elemento não existe no array.  

Características:
- Funcionam em listas ordenadas ou não
- Simples de implementar
- Não exige pré-condição

Quando faz sentido na prática
- Listas pequenas 
- Dados não ordenados
- Baixo número de buscas
- Quando simplicidade é mais importante que performance


BINÁRIA

A busca binária divide o problema pela metade a cada passo, comparando o valo buscado com o elemento central da lista. 
Pré-requisito obrigatório: a lista precisa estar **ordenada**.  

```java
public static int buscaBinaria(int[] arr, int alvo){
    int inicio = 0;
    int fim = arr.lenght - 1;
    
    while (inicio <= fim){
        int meio = inicio + (fim - inicio) / 2;
        
        if (arr[meio] ==  alvo) return meio;
        if(arr[meio] < alvo) inicio = meio +1;
        else fim = meio -1;
    }
    return -1;
}
```
Características:
- Muito mais eficiente para listas grandes
- Requer dados ordenados
- Mais complexa que a busca linear