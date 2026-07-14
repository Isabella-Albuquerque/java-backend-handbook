# Do-while

## Conceito
O do-while é uma estrutura de repetição que executa um bloco de código pelo menos uma vez e continua repetindo enquanto a condição for verdadeira.

A diferença para o while é que a condição é verificada após a execução do bloco.

## 

```java
do {
    // código a ser repetido
} while (condição);
```
## Aplicacao
é utilizado quando o bloco de código precisa ser executado pelo menos uma vez, independentemente da condição.

- Menus de aplicações em console.
- Solicitação de dados até que o usuário informe um valor válido.
- Confirmação de ações (continuar, tentar novamente, etc.).

Exemplo:
```java

Scanner scanner = new Scanner(System.in);

String senha;

do {
        System.out.print("Digite a senha: ");
senha = scanner.nextLine();
} while (!senha.equals("123456"));

        System.out.println("Acesso liberado!");
```
## Pontos de Atencao
- O bloco do do-while sempre será executado pelo menos uma vez.
- Garantir que a condição possa se tornar falsa para evitar loops infinitos.
- Atualizar corretamente a variável utilizada na condição.