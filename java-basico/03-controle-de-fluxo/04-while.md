# While

## Conceito
é uma estrutura de repetição que executa um bloco de código enquanto uma condição for verdadeira. A condição é verificada antes de cada repetição, portanto, o bloco pode não ser executado nenhuma vez caso ela seja falsa na primeira verificação.

## Sintaxe
```java
while (condição) {
    // código a ser repetido
}
```

## Aplicacoes
usado quando não se sabe previamente quantas vezes o código precisará ser executado. Aplicações comuns incluem:

- Ler dados até o usuário informar um valor válido.
- Processar uma fila enquanto houver elementos.
- Tentar estabelecer uma conexão até obter sucesso ou atingir um limite de tentativas.
- Executar um menu até o usuário escolher sair.

Exemplo:
```java
Scanner scanner = new Scanner(System.in);

int opcao = 0;

while (opcao != 4) {
    System.out.println("""
        1 - Cadastrar
        2 - Listar
        3 - Excluir
        4 - Sair
        """);

    opcao = scanner.nextInt();

    switch (opcao) {
        case 1 -> System.out.println("Cadastrando...");
        case 2 -> System.out.println("Listando...");
        case 3 -> System.out.println("Excluindo...");
        case 4 -> System.out.println("Encerrando...");
        default -> System.out.println("Opção inválida.");
    }
}
```


## Pontos de Atencao
- Loop infinito: a condição nunca se torna falsa.
- Condição incorreta, fazendo o laço executar menos ou mais vezes do que o esperado.
- Acessar posições inválidas de arrays ou listas durante a repetição.
- Modificar a condição dentro do laço de forma inadequada, gerando comportamentos inesperados.