# Matriz de diagnóstico de tarefas

Quatro perguntas, nesta ordem, para cada tarefa do mapa. A ordem importa: a solução mais simples vem primeiro. A resposta escolhe a rota — regra, IA pontual, agente ou pessoa aumentada.

## Quando usar

- O mapa de oportunidades já nomeia tarefas, não departamentos.
- Alguém pediu “um agente” para um trabalho que talvez seja uma regra.

## Quando pular

- A tarefa já tem rota escolhida e o processo não mudou.

## Antes de começar

- [Mapa de oportunidades](../discovery/opportunity-map.md).
- Para cada tarefa, um punhado de casos reais. Se duas pessoas experientes divergem nos mesmos vinte casos, há interpretação escondida na suposta regra.

## Passo a passo

1. Pegue uma tarefa por vez. Um cargo (“o analista”) não entra na matriz.
2. Responda as perguntas na ordem. Pare na primeira rota que resolve por completo.
3. Se a tarefa mistura rotas, quebre em subtarefas e classifique de novo. O pacote inteiro não herda a rota da parte mais sofisticada.
4. Antes de marcar “agente”, exija resultado verificável e erro recuperável. Sem os dois, a rota é IA pontual com revisão, ou pessoa.
5. Escreva a rota em uma frase que uma pessoa de fora entenda, sem nome de modelo.

## As quatro perguntas

| # | Pergunta | Se sim | Se não |
| :--- | :--- | :--- | :--- |
| 1 | As regras são estáveis e cabem escritas por completo? | Rota: automação determinística (regra, integração, script). Não use modelo. | Vá para a 2 |
| 2 | A tarefa exige interpretar informação não estruturada ou um padrão que não cabe em regra? | Há componente cognitivo. A pergunta 3 define se isso basta. | Se a 1 e a 2 são não, volte à tarefa: talvez ela não esteja bem cortada |
| 3 | São vários passos, com decisão no caminho, uso de sistemas, e a sequência muda caso a caso? O resultado dá para conferir e o erro dá para desfazer ou barrar antes do dano? | Rota: candidata a agente | Rota: IA pontual (classificar, extrair, resumir, rascunhar), com tratamento de erro |
| 4 | O núcleo é responsabilidade, valores, empatia ou decisão sem precedente? | Rota: aumentar a pessoa. A IA prepara. A pessoa decide e responde | A rota das perguntas anteriores permanece |

Duas tarefas tecnicamente iguais podem ter rotas diferentes se o custo do erro muda. A matriz pergunta isso na pergunta 3, antes de aceitar um agente.

## Template

**Processo:**

| Id do mapa | Tarefa | P1 regra estável? | P2 interpretação? | P3 caminho variável, verificável, recuperável? | P4 julgamento? | Rota | Como o erro aparece e quem pega |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | sim / não | sim / não | sim / não | sim / não | regra / IA pontual / agente / pessoa | |
| | | | | | | | |

**Tarefa que precisei quebrar, e em quê:**

## Exemplo preenchido — reembolso no Mercado Leme

| Id | Tarefa | P1 | P2 | P3 | P4 | Rota | Erro |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| O1 | Copiar o id do chamado para OMS e rastreio | sim | — | — | — | Regra / integração | Id inexistente volta para a fila humana |
| O2 | Aprovar ou recusar quando a política de uma página fecha | sim | — | — | — | Regra | A regra não executa pagamento nesta fase; só recomenda. Acima de R$ 80 a pessoa confirma |
| O3 | Classificar o motivo no texto livre | não | sim | não. Um passo, saída conferível por amostra | não | IA pontual | Amostra semanal. Caso ambíguo segue sem rótulo automático |
| O4 | Cruzar pedido, entrega e política quando não fecham | não | sim | sim. A sequência muda, dá para conferir as fontes, e nada é pago antes da confirmação | não, desde que a exceção saia desta tarefa | Agente, com alçada | Pagamento não dispara. Divergência sem fonte vai para a pessoa |
| O5 | Decidir exceção de lojista estratégico ou cliente de alto valor | não | sim | não cabe prescrever | sim | Pessoa. A IA só monta o resumo | A decisão não é do modelo |

O4 só permanece candidata a agente porque o pagamento fica barrado. Se o desenho exigir pagar sozinho, a resposta da pergunta 3 vira não.

## O que este template não decide

Não diz qual candidata vale o investimento, nem em que ordem construir. Agente na rota não significa agente no trimestre que vem.

## Segue para

[Matriz Impacto × Viabilidade](impact-viability.md), uma nota por linha que tenha rota.
