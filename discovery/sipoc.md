# SIPOC

Uma página com o processo inteiro: quem fornece o quê, o que entra, as etapas grandes, o que sai e quem recebe. Serve para alinhar o processo real antes de procurar um lugar para a IA.

## Quando usar

- O processo ainda não está desenhado, ou o desenho que existe é o manual, não a prática.
- O time discute o departamento (“atendimento”) e ainda não consegue apontar a saída que o cliente recebe.

## Quando pular

- Já existe um mapa do processo conferido com quem executa, atualizado nos últimos 90 dias, e a saída para o cliente está explícita.

## Antes de começar

- O nome do processo, visto pela pessoa que recebe o resultado.
- 30 a 45 minutos com alguém que executa o trabalho no dia a dia. Documentação sozinha descreve o processo idealizado.

## Passo a passo

1. Escreva o cliente e a saída primeiro. Caminhe para trás a partir do valor entregue.
2. Liste de cinco a sete etapas grandes. Cada etapa transforma uma entrada em uma saída. Clique, tela e campo ficam para depois.
3. Para cada etapa, anote quem fornece a entrada e o que precisa estar verdadeiro para a etapa começar.
4. Marque onde o item espera, volta ou muda de mão. Não resolva isso aqui.
5. Leia o SIPOC em voz alta para quem executa. Corrija o que essa pessoa não reconhecer.

## Template

**Processo:**

**Resultado para quem recebe:**

**Data e quem revisou com a operação:**

| Bloco | Conteúdo |
| :--- | :--- |
| Fornecedores | |
| Entradas | |
| Processo (5 a 7 etapas) | 1. 2. 3. 4. 5. |
| Saídas | |
| Clientes | |

**O que o manual diz e a operação não faz:**

**Onde o item mais espera:**

## Exemplo preenchido — reembolso no Mercado Leme

Marketplace. A compradora pede o dinheiro de volta depois da entrega. Volume: 1.800 solicitações por mês. Quem revisou: Marina Costa, head de pós-venda, com dois analistas, em 12 de março.

| Bloco | Conteúdo |
| :--- | :--- |
| Fornecedores | Compradora, lojista, OMS (pedidos), transportadora, helpdesk, financeiro |
| Entradas | Pedido, data de entrega, valor, texto do motivo, foto quando existe, política de reembolso |
| Processo (5 a 7 etapas) | 1. Receber a solicitação no app. 2. Localizar pedido e entrega. 3. Classificar o motivo. 4. Aplicar a política. 5. Decidir aprovar, recusar ou exceção. 6. Executar o pagamento ou a recusa. 7. Avisar compradora e lojista. |
| Saídas | Dinheiro devolvido ou recusa fundamentada, registro da decisão, aviso às duas pontas |
| Clientes | Compradora (dinheiro ou resposta), lojista (débito ou manutenção da venda), financeiro (lançamento) |

O manual descreve seis etapas lineares. Na prática, a etapa 4 para quando pedido, rastreio e texto não fecham, e o caso vai para uma fila sem dono claro. O tempo mediano até o dinheiro voltar é 2,4 dias. Cerca de 80% desse ciclo é espera, não análise. A análise humana, quando acontece, leva em média 18 minutos.

## O que este template não decide

Não escolhe tarefa candidata, rota tecnológica nem prioridade. Um SIPOC bonito sem conversa com quem executa descreve o processo que a empresa gostaria de ter.

## Segue para

[Radar de oportunidade](opportunity-radar.md), aplicado a cada etapa deste SIPOC.
