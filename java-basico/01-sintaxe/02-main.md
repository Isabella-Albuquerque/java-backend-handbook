# O Método Main
## Conceito
É o ponto de entrada da aplicação. A JVM procura o main e começã a execução por ele.

## Sintaxe
````java
public static void main(String[] args){
    
}
````
- public: A JVM precisa enxergar o método de fora da classe
- static: A JVM chama sem criar um objeto, não há instancia
- void: é um método que nada retorna para a JVM
- main: nome fixo
- String[] args: Recebe argumentos passados via linha de comando

*Nota*: A partir do Java 21 (preview) e consolidado no Java 23, ficou possível escrever "void main(){}"

Uma aplicação pode ter main em várias classes, mas o desenvolvedor define qual executar na chamada.

 