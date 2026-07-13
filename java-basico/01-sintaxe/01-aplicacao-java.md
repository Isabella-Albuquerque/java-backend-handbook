
# Estrutura de Uma Aplicação Java

## Classe (Class)
A unidade mais básica. Responsável por agrupar código, variáveis, métodos e lógica.

## Pacote (Package)
É o agrupamento lógico de classes relacionadas.

## Módulo
Conceito introduzido no Java 9. Agrupamento lógico de pacotes relacionados, é uma fronteira entre partes da aplicação. Permite decidir o que entra, o que sai, e de quem depende.

## Aplicação
conjunto de classes e pacotes (organizados ou não em módulos) que, juntos, entregam uma funcionalidade completa.

## Estrutura de Diretórios Padrão

```` java
meu-projeto/
├── src/
│   ├── main/
│   │   └── java/
│   │       └── br/com/empresa/
│   │           └── App.java        ← código-fonte
│   └── test/
│       └── java/
│           └── br/com/empresa/
│               └── AppTest.java    ← testes
├── pom.xml                         ← Maven (ou build.gradle para Gradle)
└── README.md
````

## Ciclo de Build

O compilador (Javac) transforma o texto do código em bytecode, um formato  intermediário que a JVM entende.
A JVM lê o .class em bytecode, traduz para instruções nativas do sistema operacional e do processador e executa no hardware.

``
Carro.class   ──── JVM ────▶   Execução real
(bytecode)                      (Windows, Linux, Mac...)
``
 