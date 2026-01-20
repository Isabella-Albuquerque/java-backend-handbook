# Conceitos em Java

## 1. Imutabilidade

Imutabilidade em java significa que, depois que um objeto é criado, o seu estado interno não pode ser alterado. Qualquer "mudança" resulta na criação de um novo objeto e não na modificação do existente. O que muda é apenas a referência apontando para esse novo objeto.  
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

## 2. Equals e hashCode

**Equals:** é um método usado para dizer quando dois objetos devem ser considerados "iguais" em termos de negocio e nao apenas se sao o mesmo objeto na memória.
Object.equals compara referencia. 
```java
Object a = new Object();
Object b = new Object();
a.equals(b); //false

```
**HashCode:** é um numero inteiro que representa o objeto e é usado por estruturas de dados baseadas em hash (HashMap, HashSet).

Ele não garante unicidade, mas:
- objetos iguais devem ter o mesmo hashCode

Em java: 
- Precisamos comparar objetos semanticamente
- Armazenar objetos eficientemente em coleções

Sem isso:
-HashMap

Se dois objetos são iguais pelo equals, eles DEVEM ter o mesmo hashCode.
