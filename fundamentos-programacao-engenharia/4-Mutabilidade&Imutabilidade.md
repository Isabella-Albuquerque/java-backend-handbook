# Conceitos em Java

## 1. Imutabilidade

Imutabilidade em java significa que, depois que um objeto é criado, 
o seu estado interno não pode ser alterado. Qualquer "mudança" resulta na criação de um novo objeto e não na
modificação do existente. O que muda é apenas a referência apontando para esse novo objeto. 
O custo pode ser mais alocações, mas a JVM lida bem com isso, e em muitos casos o ganho em segurança e simplicidade compensa. 

Garante:
- previsibildiade
- seguranca em ambientes concorrentes
- evita efeitos colaterais
- objetos imutáveis são thread-safe por definição
- facilita testes

**Exemplo:**
String: ao concatenar, um novo objeto é criado.
```java
String nome = "Isa";
nome = nome.concat(" Albuquerque");
```
O que acontece:

- "Isa" é criado no heap
- "Isa Albuquerque" é criado como outro objeto
- A variável nome passa a apontar para o novo objeto
- O objeto "Isa" continua intacto

String, Integer, LocalDate, BigDecimal são imutáveis

#### Mitos Comuns

**1- “Objeto imutável nunca sai da memória”**
imutável ≠ eterno.
Tempo de vida é do GarbageCollector, não da mutabilidade.


Variáveis mudam referências.
Objetos mudam estado.
Imutabilidade fala do estado do objeto.