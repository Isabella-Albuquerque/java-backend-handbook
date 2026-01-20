# Fundamentos de Programação e Engenharia

## 1. Pensamento Computacional

Pensamento computacional é a capacidade de formular problemas de forma clara e estruturada, de modo que:
- outro ser humano consiga entendê-los
- uma máquina consiga executá-los.

Ele se sustenta em quatro pilares:
- Decomposição
- Reconhecimento de Padrões
- Abstração
- Algoritmização

---

## Decomposição

É a estratégia de dividir um problema grande em partes menores, até que cada parte seja simples o suficiente para ser resolvida sem esforço cognitivo excessivo.

### Exemplo de problema
Criar uma API para registrar uma compra.

### Abordagem com decomposição
1. Refletir sobre o significado da ação “registrar uma compra”
2. Listar os passos obrigatórios
3. Antecipar falhas e cenários de erro

### Possível decomposição
- Validar dados de entrada
- Verificar cliente
- Verificar produtos
- Calcular total
- Persistir a compra
- Retornar resposta

### Características de uma boa decomposição
- Cada parte tem uma única responsabilidade
- Pode ser explicada em uma frase curta
- Pode ser testada isoladamente
- Pode virar um método ou função sem esforço

📌 Todo problema computacional pode ser visto como:
- Entrada → dados recebidos
- Processamento → regras e transformações
- Saída → resultado

**Exemplo simples: “Calcular o total de um carrinho”**
- Entrada: lista de itens
- Processamento: soma de preços + regras
- Saída: valor total

---

## Reconhecimento de Padrões

Habilidade de identificar estruturas recorrentes em problemas diferentes e perceber que eles podem ser resolvidos com a mesma lógica geral, ainda que o contexto mude.

### Importância
- Reduz esforço cognitivo
- Acelera a resolução de problemas
- Melhora o design do sistema
- Evita código duplicado

### Exemplos de padrões comuns
- Validação de entrada
- Comparação de valores
- Fluxos com múltiplas decisões
- Pipeline (entrada → transformação → saída)

---

## Abstração

É a habilidade de focar apenas no que é relevante em um determinado nível, escondendo detalhes que não importam naquele momento.

Abstrair é delimitar responsabilidades.

### Exemplo
Para enviar um e-mail não é necessário compreender como funciona o sistema de envio em nível técnico, apenas o passo a passo necessário para concluir a tarefa com sucesso.

### Níveis de abstração
1. Problema (alto nível)  
   O que precisa ser resolvido. Linguagem do negócio, sem detalhes técnicos.

2. Modelo / Lógica  
   Como o problema será resolvido de forma geral (fluxos, regras, ideia do algoritmo).

3. Algoritmo  
   Passo a passo da solução, ainda independente de linguagem.

4. Implementação (baixo nível)  
   Código, linguagem, frameworks e banco de dados.

5. Execução (máquina)  
   Como o computador realmente executa o código (memória, CPU, sistema operacional).

---

## Algoritmização (sem código)

É a capacidade de definir uma sequência clara e finita de passos, considerando:
- Ordem
- Decisões
- Possíveis falhas

### Características de um bom algoritmo
- Passos claros
- Ordem explícita
- Não depende de tecnologia
- Considera cenários inválidos
- Possui início, meio e fim

### Exemplo: “Processar login”
1. Receber credenciais
2. Verificar existência do usuário
3. Validar senha
4. Verificar permissões
5. Retornar sucesso ou erro  
