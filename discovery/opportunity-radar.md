# Radar de oportunidade

Um checklist para marcar, em cada etapa do processo, onde a automação inteligente tende a gerar valor — e onde a resposta certa é não usar IA. O radar indica onde olhar. A decisão de construir vem depois.

## Quando usar

- O SIPOC já existe e você precisa escolher quais etapas merecem uma investigação de tarefa.
- O pedido que chegou foi “vamos colocar um agente aqui” e ainda não há critério para concordar ou recusar.

## Quando pular

- A etapa já passou pelo radar nesta rodada e o processo não mudou.

## Antes de começar

- [SIPOC](sipoc.md) revisado com quem executa.
- Uma estimativa, mesmo grosseira, de volume, tempo de espera e onde os dados ficam. Número desconhecido entra como premissa, não como zero.

## Passo a passo

1. Percorra uma etapa de cada vez. “Automatizar o atendimento” não é uma etapa.
2. Marque cada sinal como presente, fraco ou ausente. Anote a evidência ao lado.
3. Aplique o contracheck na mesma etapa. Um sinal forte não sobrevive a um contracheck que manda parar.
4. Siga um item real (um pedido, um chamado) e separe tempo trabalhado de tempo esperando.
5. Leve para o mapa só as etapas com pelo menos dois sinais presentes e nenhum contracheck bloqueando. As bloqueadas ficam numa lista de pendência, com o que precisaria mudar.

## Os cinco sinais

| Sinal | Presente quando | Evidência que vale |
| :--- | :--- | :--- |
| Volume com repetição | A etapa acontece dezenas ou milhares de vezes num período, com um padrão reconhecível | Contagem no sistema, não a memória de um dia atípico |
| Regra clara ou padrão aprendível | Dá para escrever a regra, ou um especialista acerta de forma consistente sem conseguir escrever a regra inteira | Página de regras, ou vinte casos julgados por duas pessoas |
| Dados disponíveis | Existe rastro digital da etapa e alguém pode mostrar uma amostra | Amostra real em uma semana. Discurso sem amostra conta como ausente |
| Fricção | Espera, retrabalho, erro ou redigitação visíveis no fluxo | Tempo de fila, taxa de devolução, custo de um erro |
| Linguagem não estruturada | Alguém lê, interpreta ou escreve texto livre, documento ou conversa | Exemplo de mensagem, contrato ou nota |

## Contracheck — quando não usar IA

Pare a etapa se qualquer linha for verdadeira. Registre a pendência em vez de forçar a oportunidade.

| Contracheck | O que fazer em vez de IA |
| :--- | :--- |
| O processo está quebrado: regras contraditórias, dono difuso, exceção que ninguém explica | Arrumar o processo. Automação em cima de regra contraditória acelera o erro |
| A decisão cabe numa página de regras estáveis | Implementar a regra em código, fluxo ou validação. Modelo probabilístico aqui é custo sem ganho de acerto |
| O erro é caro e pouco reversível (crédito, diagnóstico, sanção, pagamento alto, efeito jurídico) | A IA pode preparar. A pessoa decide |
| A presença humana é o que o cliente compra (negociação de alto valor, notícia difícil, cuidado) | Não substituir a conversa. No máximo, preparar contexto para a pessoa |
| Não há dados e não há como instrumentar, ou nenhuma área assume o resultado | Fica fora do mapa até existir amostra e dono |

## Template

**Processo (do SIPOC):**

| Etapa | Volume | Regra ou padrão | Dados | Fricção | Linguagem | Contracheck | Segue para o mapa? |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | | | | | | sim / pendência / não |
| | | | | | | | |
| | | | | | | | |

**Premissas** (o que ainda não medimos):

**Pendências** (o que bloqueia, e quem desbloqueia):

## Exemplo preenchido — reembolso no Mercado Leme

| Etapa | Volume | Regra ou padrão | Dados | Fricção | Linguagem | Contracheck | Segue? |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Receber a solicitação | 1.800/mês | Formulário fixo | Helpdesk | Baixa | Texto do motivo | Nenhum | Não. A etapa já é automática |
| Localizar pedido e entrega | 1.800/mês | Consulta por id | OMS e rastreio, API | Analista redigita o id | Não | Nenhum | Sim, como regra ou integração, não como modelo |
| Classificar o motivo | 1.800/mês | Padrão aprendível; duas pessoas concordam em 8 de 10 casos | Texto do chamado; rótulo em 70% do log de 14 meses | 6 min por caso | Sim | Nenhum | Sim |
| Aplicar a política nos casos claros | 990/mês (55%) | Cabe numa página: menos de 7 dias, lacrado, primeira vez, até R$ 80 | Pedido, data, valor, histórico | Espera de 2,4 dias no ciclo | Não | A regra basta. Não usar modelo | Sim, como regra |
| Resolver pedido, entrega e política que não fecham | 320/mês | Caminho muda caso a caso | Log incompleto; política e OMS existem | 45 min; erro médio de R$ 70 | Sim | Erro de pagamento é reversível só antes do envio | Sim, com supervisão |
| Exceção de lojista estratégico ou cliente de alto valor | 90/mês | Não há regra estável | Histórico parcial | Alta, mas rara | Sim | Julgamento e precedente. Pessoa decide | Sim, só como preparação para a pessoa |
| Recusar pelo tom da mensagem | — | Não | Não | — | Sim | Erro reputacional e sem dono de política | Não. Pendência permanente |

## O que este template não decide

Não ranqueia oportunidades, não estima retorno e não desenha o agente. Dois sinais acesos não significam “construir um agente”.

## Segue para

[Mapa de oportunidades](opportunity-map.md), uma linha por etapa que passou.
