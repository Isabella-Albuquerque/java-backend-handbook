
# Introducao ao Spring

## Conceito
Spring é um framework de infraestrutura para aplicações Java.   
Seu objetivo é facilitar a forma como organizar, criar, conectar e gerenciar objetos de forma desacoplada, testável e escalável. 
Ele fornece um container (núcleo do spring) para gerenciar objetos, suas dependências e seu ciclo de vida.

---

## IoC (Inversion of Control) e Injeção de Dependência
Em Java 'puro' o código controla tudo sozinho: 
- quando o objeto nasce, como, quais dependencias ele usa e quando morre. 

No Spring:
- o container controla o ciclo de vida
- o desenvolvedor apenas declara as intenções

Dessa forma, você nao usa new em codigo de negocio, mas sim declara dependencias. 

**Exemplo Prático**
Utilizando puramente Java:
```java
public class EmailService {
    public void enviar(String mensagem) {
        System.out.println("Enviando email: " + mensagem);
    }
}

```

```java
public class PedidoService {

    private EmailService emailService;

    public PedidoService() {
        this.emailService = new EmailService();
    }

    public void criarPedido() {
        emailService.enviar("Pedido criado");
    }
}

```
- Aqui a propria classe PedidoService cria o EmailService
- Existe forte dependencia entre as classes (acoplamento)
- A classe controla suas dependencias (objetos que uma classe precisa para funcionar)


Utilizando Spring:
```java

@Service
public class EmailService {
    public void enviar(String mensagem) {
        System.out.println("Enviando email: " + mensagem);
    }
}

```

```java
@Service
public class PedidoService {

    private final EmailService emailService;

    public PedidoService(EmailService emailService) {
        this.emailService = emailService;
    }

    public void criarPedido() {
        emailService.enviar("Pedido criado");
    }
}

```
- Usando Spring o container cria e gerencia os objetos 
- PedidoService não cria o EmailService, apenas declara a dependência 
- O Spring injeta automaticamente o EmailService 
- O código fica desacoplado, testável e mais fácil de evoluir


Em resumo:   
Java puro: a classe cria suas dependências.
Spring: o container cria e injeta as dependências.

---

### Classe