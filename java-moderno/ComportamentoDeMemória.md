# Java Moderno – Resumo

## 1. Comportamento de Memória
Em Java, as variáveis não armazenam diretamente objetos, mas sim valores. O que muda é o tipo do valor armazenado:

valor primitivo ou

referência a um objeto.

O gerenciamento de memória é feito automaticamente pela JVM, com uso de Heap, Stack e Garbage Collector.

### Tipo Referência VS Tipo Valor

Classes são tipos referência. Dentro dela se referencia o endereco de memória que aponta pra onde está o objeto. 

p2 = p1 ;
p2 passa a apontar para onde p1 aponta. Dentro da variavel de p2 haverá o mesmo endereco de p1
Alocação Dinâmica de Memória

Valor "null"
Tipo referencia aceitam o valor "null" que indica que a variavel aponta pra ninguem

Tipos primitivos sao tipos valor: tipos valor são caixas e nao ponteiros.

double x, y;
x = 10; x recebe efetivamente 10
y = x; y recebe uma cópia de x ou seja, o valor 10 em si

Tipos Primitivos e Inicialização
int p;
System.out.pRINCILN(P); -> ERRO
a variável precisa ser inicializada, ou seja...
