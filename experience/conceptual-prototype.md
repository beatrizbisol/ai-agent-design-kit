# Protótipo conceitual

O comportamento da solução, escrito para alinhar negócio, engenharia e operação antes de tela, prompt ou integração. Diz o que ela entende, o que decide, o que entrega e quando para.

## Quando usar

- O [storyboard](storyboard.md) já cabe numa leitura de um minuto.
- O time vai começar a especificar campos, mensagens ou serviços e ainda não há acordo sobre limites.

## Quando pular

- Você está mudando só a cópia de uma mensagem, e papel, entradas e escalonamento continuam os do protótipo vigente.

## Antes de começar

- Storyboard e [brief](../use-case/brief.md), inclusive o que esta versão não faz.
- A rota do [diagnóstico](../diagnosis/task-diagnosis-matrix.md). Se a rota é regra, o protótipo não ganha “entendimento” de texto livre por enfeite.

## Passo a passo

1. Escreva papel, objetivo e limite em frases observáveis. “Agente inteligente” não serve. Diga o trabalho: recomendar a política clara, por exemplo.
2. Liste entradas obrigatórias e o que acontece se uma falta. Falta de dado não é licença para completar com suposição.
3. Descreva a decisão: qual evidência, qual regra ou critério, o que fica registrado.
4. Preencha a matriz de escalonamento. Cada situação tem uma ação: responder, pedir dado, explicar o limite ou pedir aprovação.
5. Marque o que está explicitamente fora. Limite é parte do desenho, não um apêndice.
6. Separe este protótipo do visual e do funcional. Conceitual fecha a lógica. Visual mostra mensagens e estados. Funcional simula com dado real. Só então um piloto.
7. Confira contra o storyboard. Se um quadro não tem lugar aqui, ou o quadro sai, ou o protótipo está incompleto.

## Template

**Iniciativa:**

**Papel (observável):**

**Objetivo:**

**Não faz:**

| Pergunta | Resposta |
| :--- | :--- |
| Quem usa? | |
| Que informação recebe? | |
| Que decisão toma? | |
| Quando para e escala? | |

**Entradas**

| Entrada | Obrigatória? | Se faltar |
| :--- | :--- | :--- |
| | | |

**Saídas**

| Saída | Para quem | O que fica registrado |
| :--- | :--- | :--- |
| | | |

**Capacidades desta versão** (risque as que não existem ainda): entender / orientar / recomendar / executar

### Matriz de escalonamento

| Situação | Ação |
| :--- | :--- |
| Dados suficientes e regra clara | |
| Dado incompleto | |
| Ambíguo ou sem critério estável | |
| Impacto sensível (dinheiro, pessoa, irreversível, jurídico) | |

**Integrações necessárias só para esta versão:**

**Como saber que o protótipo está errado** (ligado à métrica do brief):

## Exemplo preenchido — reembolso no Mercado Leme

**Papel:** recomendar aprovar ou recusar o reembolso quando os quatro campos da política clara fecham.

**Objetivo:** o analista confirma a partir da evidência, sem reler a política nem copiar o id.

**Não faz:** pagar, falar com a compradora, ler o texto para decidir, julgar exceção, investigar divergência.

| Pergunta | Resposta |
| :--- | :--- |
| Quem usa? | Analista de reembolso, dentro do chamado |
| Que informação recebe? | Id do pedido, data de entrega, valor, flag de primeira solicitação, status de entrega |
| Que decisão toma? | Recomenda aprovar só se os quatro critérios da política fecham. Caso contrário, não recomenda |
| Quando para e escala? | Campo ausente, valor acima de R$ 80, exceção marcada, ou qualquer pagamento |

**Entradas**

| Entrada | Obrigatória? | Se faltar |
| :--- | :--- | :--- |
| Id do pedido | sim | Sem recomendação |
| Data de entrega | sim | Sem recomendação |
| Valor | sim | Sem recomendação |
| Primeira solicitação | sim | Sem recomendação |
| Status de entrega | sim | Sem recomendação |
| Texto do motivo | não | Ignorado nesta versão |

**Saídas**

| Saída | Para quem | Registro |
| :--- | :--- | :--- |
| Recomendação aprovar ou silêncio | Analista, no chamado | Campos lidos, item da política, versão da regra, horário |
| Confirmação humana | Fila de pagamento já existente | Id de quem confirmou |

**Capacidades desta versão:** recomendar. Não executa.

### Matriz de escalonamento

| Situação | Ação |
| :--- | :--- |
| Dados suficientes e regra clara | Recomenda aprovar e mostra os campos. Não paga |
| Dado incompleto | Não recomenda. O chamado segue na fila humana |
| Ambíguo ou sem critério estável | Não recomenda. Texto livre não desempata |
| Impacto sensível | Pagamento, valor acima de R$ 80 e exceção ficam com a pessoa |

**Integrações:** leitura no OMS e no rastreio. Nenhuma escrita em pagamento.

**Como saber que está errado:** em 200 casos rotulados, alguma recomendação discorda da política escrita; ou, em produção, mais de 5% de discordância com o analista em 8 semanas.

## O que este template não decide

Não escolhe topologia, memória, ferramenta ou modelo, e não autoriza o horizonte seguinte. Também não é uma tela.

## Segue para

[Roadmap de 3 horizontes](../evolution/three-horizons.md), para dizer o que esta versão já precisa ter e o que fica para depois.
