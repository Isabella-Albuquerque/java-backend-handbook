# Métodos em POO

## Conceito

Métodos representam os **comportamentos** de um objeto. Eles definem as ações que uma instância pode executar e as regras de negócio associadas ao seu estado.

Em POO, os métodos devem manipular os atributos do próprio objeto, preservando o encapsulamento e a consistência do estado.

---

## Estrutura de um método

Um método é composto por:
- modificador de acesso;
- tipo de retorno;
- nome;
- parâmetros (opcional);
- corpo.

```java
public void activate() {
    this.active = true;
}
```

---

## Tipos de métodos

### Métodos de instância

Operam sobre os atributos de uma instância específica.

```java
public class User {

    private boolean active;

    public void activate() {
        this.active = true;
    }
}
```

---

### Métodos estáticos (`static`)

Pertencem à classe e podem ser chamados sem criar uma instância.

```java
public class MathUtils {

    public static int sum(int a, int b) {
        return a + b;
    }
}
```

Uso:

```java
MathUtils.sum(10, 5);
```

---

## Retorno

Um método pode retornar um valor:

```java
public String getEmail() {
    return email;
}
```

Ou não retornar nenhum valor (`void`):

```java
public void deactivate() {
    this.active = false;
}
```

---

## Parâmetros

Permitem que o método receba informações para executar sua lógica.

```java
public void changeEmail(String newEmail) {
    this.email = newEmail;
}
```

---

## Boas práticas

- [x] Métodos devem representar ações do domínio.
- [x] Dar nomes que expressem claramente a intenção (`activate()`, `calculateTotal()`).
- [x] Manter métodos pequenos e com uma única responsabilidade.
- [x] Evitar métodos com muitos parâmetros.
- [x] Sempre que possível, deixar o próprio objeto responsável por alterar seu estado.