
# Encapsulamento
É um princípio que consiste em esconder detalhes de implementação de uma classe, expondo apenas operações seguras e que mantenham os objetos em um estado consistente.

Encapsulamento = controlar acesso ao estado interno.

O objeto decide como e quando seu estado pode mudar.

É base para baixo acoplamento.

Regra Geral Basica:
- um objeto *não* deve expor nenhum atributo(usar modificador de acesso private)


### Erros comuns
Expor campos como public.

Getter e setter para tudo, sem regra.

Permitir estado inválido temporário.

Validar fora do objeto (em controller/service).

### Boas práticas
Campos sempre private.

Métodos expressam intenções, não operações genéricas.

Preferir métodos como activate(), cancel(), close() em vez de setters.

Invariantes protegidas internamente.

### Impacto arquitetural
Encapsulamento forte → domínio mais estável.

Menos efeitos colaterais.

Testes focam em comportamento, não implementação.

```java
private String name;

public Strin getName(){
    return name;
}

public void setName(String name){
    this.name = name:
}
```