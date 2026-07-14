# Modificadores de Acesso

## Conceito

Modificadores de acesso definem **a visibilidade e o nível de acesso** que classes, atributos, métodos e construtores possuem dentro de uma aplicação.

Eles são fundamentais para aplicar **encapsulamento**, controlando quais partes do sistema podem acessar ou modificar determinados elementos.

---

## Tipos de modificadores

### `public`

Permite acesso de qualquer lugar da aplicação.

```java
public class User {
    public String name;
}
```

Uso comum:
- classes públicas;
- métodos que fazem parte da API da classe.

---

### `private`

Permite acesso apenas dentro da própria classe.

```java
public class User {

    private String password;

}
```

Uso comum:
- atributos;
- proteger o estado interno do objeto.

É o modificador mais utilizado para atributos em POO.

---

### `protected`

Permite acesso:
- dentro da própria classe;
- classes do mesmo pacote;
- subclasses.

```java
protected String id;
```

Uso comum:
- herança.

---

### Sem modificador (package-private)

Quando nenhum modificador é declarado, o acesso fica limitado ao mesmo pacote.

```java
String email;
```

Uso comum:
- compartilhar elementos entre classes relacionadas dentro do mesmo pacote.

---

## Níveis de acesso

| Modificador | Classe | Pacote | Subclasse | Mundo |
|---|---|---|---|---|
| public | ✓ | ✓ | ✓ | ✓ |
| protected | ✓ | ✓ | ✓ | ✗ |
| package-private | ✓ | ✓ | ✗ | ✗ |
| private | ✓ | ✗ | ✗ | ✗ |

---

## Boas práticas

- [x] Preferir `private` para atributos.
- [x] Expor apenas o necessário.
- [x] Evitar criar atributos públicos.
- [x] Usar métodos para controlar alterações no estado do objeto.
- [x] Reduzir o acoplamento entre classes através do controle de acesso.