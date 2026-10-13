# Mapa de oportunidades

A lista que sai da descoberta. Cada linha é uma oportunidade no nível da tarefa, com a fricção, os sinais, os dados e o dono. Não tem fornecedor, modelo nem ferramenta.

## Quando usar

- O radar já separou o que segue do que fica pendente.
- Você precisa de uma lista que caiba numa conversa de priorização, não de um inventário de ideias.

## Quando pular

- A lista já tem fricção medida, dados localizados e dono nomeado, e o processo não mudou.

## Antes de começar

- [SIPOC](sipoc.md) e [radar](opportunity-radar.md).
- Uma pessoa da operação disposta a confirmar a fricção. Mapa feito só de slide descreve o processo oficial.

## Passo a passo

1. Abra uma linha só para etapa que o radar mandou seguir.
2. Troque o nome da etapa pela tarefa. “Analisar reembolso” vira “classificar o motivo escrito pela compradora”.
3. Escreva a fricção com número: vezes, minutos, dias de espera, custo de um erro. Se o número é premissa, marque como premissa.
4. Aponte onde estão os dados e quem autoriza o uso. Sem amostra, a linha continua no mapa com a viabilidade em aberto — não invente a fonte.
5. Nomeie o dono do resultado. Área inteira (“o pós-venda”) não conta.
6. Prefira oito linhas investigadas a quarenta linhas rasas. Corte a linha que não tem fricção nem dono.
7. Deixe de fora qualquer menção a modelo, fornecedor ou “vamos usar um agente”. A rota é o próximo template.

## Template

**Processo:**

**Quem confirmou a operação:**

| Id | Etapa | Tarefa candidata | Fricção observada | Sinais presentes | Dados e dono dos dados | Dono do resultado |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| O1 | | | | | | |
| O2 | | | | | | |
| O3 | | | | | | |

**Fora do mapa nesta rodada, e por quê:**

**Premissas:**

## Exemplo preenchido — reembolso no Mercado Leme

Confirmado com Marina Costa e dois analistas.

| Id | Etapa | Tarefa candidata | Fricção observada | Sinais presentes | Dados e dono dos dados | Dono do resultado |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| O1 | Localizar pedido e entrega | Copiar id do chamado para o OMS e o rastreio | 1.800/mês, redigitação, parte da espera de 2,4 dias | Volume, dados, fricção | OMS e rastreio. Dono: operação de pedidos | Marina Costa |
| O2 | Aplicar a política nos casos claros | Aprovar ou recusar quando a regra da página fecha | 990/mês; 18 min de análise; espera domina o ciclo | Volume, regra, dados, fricção | Pedido, data, valor, histórico. Dono: OMS | Marina Costa |
| O3 | Classificar o motivo | Ler o texto e marcar defeito, arrependimento, item errado ou atraso | 1.800/mês; cerca de 6 min; rótulo existe em 70% do log | Volume, padrão, dados parciais, linguagem | Texto no helpdesk. Dono: pós-venda | Marina Costa |
| O4 | Resolver divergência | Cruzar pedido, entrega e política quando os três não fecham | 320/mês; 45 min; erro médio de R$ 70 | Volume moderado, padrão parcial, fricção, linguagem | Log cobre 70%. Política e OMS existem. Dono dos rótulos: pós-venda | Marina Costa |
| O5 | Exceção | Preparar o caso de lojista estratégico ou cliente de alto valor para uma pessoa decidir | 90/mês; a decisão em si é curta, a coleta é que consome o tempo | Linguagem, fricção | Histórico parcial. Dono: pós-venda | Marina Costa |

**Fora do mapa:** recusar pelo tom da mensagem. Não há política, o erro é público e ninguém assume o resultado.

**Premissas:** os 18 minutos e os 45 minutos vêm de observação de uma semana (40 casos), não de um ano inteiro. A hora do analista usada adiante é R$ 45, custo interno informado pelo financeiro.

## O que este template não decide

Não diz se a tarefa pede regra, IA pontual, agente ou pessoa. Não calcula retorno. Uma linha no mapa é uma candidata, não um projeto aprovado.

## Segue para

[Matriz de diagnóstico de tarefas](../diagnosis/task-diagnosis-matrix.md), uma passagem por linha deste mapa.
