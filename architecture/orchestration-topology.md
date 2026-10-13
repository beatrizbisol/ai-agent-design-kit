# Topologia de orquestração

A forma como o trabalho se divide entre passos e, se houver mais de um agente, entre eles. A escolha vale para o horizonte que está em construção, não para a visão final.

## Quando usar

- O [protótipo](../experience/conceptual-prototype.md) e o [horizonte 1](../evolution/three-horizons.md) já dizem o que esta versão faz.
- Alguém propôs vários agentes, um grafo ou um enxame antes de a sequência caber numa lista.

## Quando pular

- A versão é uma única regra ou uma única chamada, sem ramificação. Registre “um passo” e siga para memória e ação. Topologia de multiagente seria teatro.

## Antes de começar

- Protótipo conceitual, em especial a matriz de escalonamento.
- O que o horizonte atual deixa de fora. Topologia não puxa esse fora para dentro.

## Passo a passo

1. Escreva a sequência desta versão em passos. Se a sequência é a mesma em todo caso que passa, a topologia é workflow.
2. Se há ramos e paralelismo de verdade (não só um if de “falta dado”), considere grafo. Desenhe os ramos que existem hoje, não os que o horizonte 3 talvez tenha.
3. Use hierarquia só quando um orquestrador delega um subtrabalho com contrato claro. “Agente que chama ferramenta” não é, sozinho, hierarquia de agentes.
4. Use enxame só quando vários trabalhadores compartilham um objetivo e o resultado emerge da divisão, e você aceita menos previsibilidade. Para fluxo auditável de negócio, isso quase nunca é a primeira escolha.
5. Escreva por que as outras três ficaram de fora. A frase “vamos precisar no futuro” não escolhe a topologia de agora.
6. Aponte onde a pessoa entra. Esse ponto tem que coincidir com o storyboard.

## As quatro formas

| Forma | Cabe quando | Custa |
| :--- | :--- | :--- |
| Workflow | Passos fixos, mesma ordem, trilha fácil de auditar | Pouca flexibilidade. Um caso fora do roteiro precisa de saída explícita |
| Grafo | Ramos, voltas e paralelismo que não cabem numa linha | Mais caminhos para testar. Cada aresta precisa de condição |
| Hierárquico | Um orquestrador delega a agentes com contrato de entrada e saída | O orquestrador vira ponto único de falha e de custo |
| Enxame | Objetivo comum, papéis sobrepostos, resultado emergente | Difícil de explicar por que um caso deu naquela saída |

## Template

**Versão (horizonte):**

**Passos desta versão, na ordem:**

1.

**Forma escolhida:**

**Por que as outras não:**

**Onde a pessoa entra:**

**O que esta topologia não faz ainda:**

## Exemplo preenchido — reembolso no Mercado Leme

**Versão:** horizonte 1, O2.

**Passos:**

1. Receber o id do chamado.
2. Ler pedido e entrega.
3. Se faltar campo, parar sem recomendação.
4. Aplicar a política clara.
5. Se fechar, gravar a recomendação no chamado. Se não fechar, silêncio.
6. Analista confirma. O pagamento segue na fila humana, fora desta orquestração.

**Forma escolhida:** workflow.

**Por que as outras não:** não há ramo paralelo. O “não fecha” é uma saída do mesmo fluxo, não um segundo agente. Hierarquia e enxame apareceriam se o horizonte 3 investigasse divergência com mais de um trabalhador. Não é esta versão.

**Onde a pessoa entra:** depois do passo 5, antes de qualquer dinheiro.

**O que não faz ainda:** classificar texto, chamar lojista, pagar.

## O que este template não decide

Não escolhe o que fica na memória, quais ações existem nem qual motor executa o passo 4.

## Segue para

[Desenho de memória](memory.md).
