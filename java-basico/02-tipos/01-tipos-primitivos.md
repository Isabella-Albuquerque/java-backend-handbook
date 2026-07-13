# Tipos Primitivos

## Conceito
São os tipos mais básicos da linguagem. Não são objetos.
- vivem diretamente na memória sem overhead de classe.

## Principais Tipos

| Tipo | Tamanho | Valor Mínimo | Valor Máximo | Valor Padrão | Exemplo de Uso |
|---|---|---|---|---|---|
| `byte` | 8 bits | -128 | 127 | `0` | `byte idade = 25;` |
| `short` | 16 bits | -32.768 | 32.767 | `0` | `short ano = 2024;` |
| `int` | 32 bits | -2.147.483.648 | 2.147.483.647 | `0` | `int estoque = 1000;` |
| `long` | 64 bits | -9.223.372.036.854.775.808 | 9.223.372.036.854.775.807 | `0L` | `long populacao = 8_000_000_000L;` |
| `float` | 32 bits | ~1.4 × 10⁻⁴⁵ | ~3.4 × 10³⁸ | `0.0f` | `float temperatura = 36.5f;` |
| `double` | 64 bits | ~4.9 × 10⁻³²⁴ | ~1.8 × 10³⁰⁸ | `0.0` | `double preco = 4500.90;` |
| `char` | 16 bits | `'\u0000'` (0) | `'\uffff'` (65.535) | `'\u0000'` | `char inicial = 'J';` |
| `boolean` | 1 bit | — | — | `false` | `boolean ativo = true;` |

 