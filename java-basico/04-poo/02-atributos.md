# Atributos em POO

## Conceito

Atributos são as **características (estado)** de um objeto. Eles armazenam as informações que representam as propriedades de uma instância e definem sua condição em determinado momento da execução.

Cada objeto possui sua própria cópia dos atributos de instância, enquanto atributos estáticos são compartilhados por todas as instâncias da classe.

---

## Tipos de atributos

### Atributos de instância

Pertencem ao objeto e cada instância possui seus próprios valores.

```java
public class User {
    private String name;
    private String email;
}
```

Cada objeto `User` possui seu próprio `name` e `email`.

---

### Atributos estáticos (`static`)

Pertencem à classe e são compartilhados entre todas as instâncias.

```java
public class User {
    public static final String SYSTEM_NAME = "Finance API";
}
```

O atributo pode ser acessado sem criar um objeto.

```java
User.SYSTEM_NAME;
```

---

## Modificadores de acesso

Os atributos normalmente são declarados como `private`, impedindo acesso direto por outras classes.

```java
private String email;
```

O acesso deve ocorrer por meio de métodos da própria classe quando necessário.

---

## Boas práticas

- [x] Declarar atributos como `private` para garantir encapsulamento.
- [x] Utilizar nomes claros que representem o domínio.
- [x] Evitar atributos públicos (`public`).
- [x] Tornar atributos `final` quando não precisarem ser alterados.
- [x] Manter apenas os atributos necessários para representar o estado do objeto.