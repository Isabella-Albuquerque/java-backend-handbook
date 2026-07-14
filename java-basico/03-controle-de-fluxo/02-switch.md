# Switch

## Conceito
O switch e uma estrutura de decisao que serve para escolher um entre 
vários caminhos possíveis com base no valor de uma única variável.

## Sintaxe
````java
switch (expressao) {
    case valor1:
        // código
        break;

    case valor2:
        // código
        break;

    default:
        // código executado se nenhum case for atendido
}
````

## Aplicacoes

A indicacao do switch e para casos em que uma única variável pode assumir vários valores conhecidos e cada valor exige uma ação diferente.

Exemplos

 - Tipos de Pagamento 
```java
 switch (tipoPagamento) {
        case PIX -> pagarComPix();
    case CARTAO -> pagarComCartao();
    case BOLETO -> pagarComBoleto();
}
 ```

## Pontos de Atencao

- Usar switch para regras de negócio complexas. 
- Escrever dezenas de case quando um Map ou polimorfismo seria mais adequado. 
- Repetir código em vários casos.