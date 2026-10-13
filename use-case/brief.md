# Brief de caso de uso

Uma página por iniciativa, antes de qualquer construção. Amarra o problema medido, a rota mais simples, a métrica, a autonomia e o critério para encerrar. Se não cabe numa leitura de cinco minutos, ainda está vago.

## Quando usar

- A iniciativa já está na coluna Agora do [AI-RICE](../diagnosis/ai-rice.md).
- Negócio e engenharia precisam do mesmo ponto de partida.

## Quando pular

- A iniciativa ainda não passou pelos eliminatórios de dado e dono. Volte à matriz. Brief de ideia sem dono vira piloto zumbi.

## Antes de começar

- [Mapa](../discovery/opportunity-map.md), [diagnóstico](../diagnosis/task-diagnosis-matrix.md) e [AI-RICE](../diagnosis/ai-rice.md) da mesma tarefa.
- [Stakeholders e riscos](stakeholders-and-risks.md) pelo menos em rascunho. O brief aponta para esse mapa em vez de repetir a governança inteira.

## Passo a passo

1. Escreva o problema com número. Se a frase cabe em qualquer empresa, ainda não é o problema.
2. Desça com JTBD e, se o pedido original veio como solução, com os 5 Porquês. Pare quando a causa explicar a fricção do mapa. Não transforme os porquês num projeto paralelo.
3. Declare a tarefa e a rota. Se uma regra resolve, o brief é de uma regra. Agente entra só quando o diagnóstico chegou nessa rota e nenhuma rota anterior resolveu.
4. Descreva quem usa e em que ponto do fluxo real a solução aparece. Ferramenta em outra aba, que a pessoa precisa lembrar de abrir, fica fora.
5. Feche a métrica de negócio: linha de base, alvo e quando medir. Ao lado, a métrica técnica que sustenta esse alvo. Acurácia sem efeito no processo não é sucesso.
6. Fixe a autonomia desta versão: o que a solução decide, o que só recomenda, o que uma pessoa sempre faz.
7. Liste dados, dono e qualidade. Aponte os riscos principais para o mapa de stakeholders, com a salvaguarda desta versão.
8. Nomeie uma pessoa dona do resultado e o critério de encerramento. Sem esse critério, o piloto que não funciona continua consumindo gente.
9. Faça a conta simples de retorno: valor anual ÷ custo total (construir + operar). Registre em quanto tempo o valor aparece. Hora economizada só entra se alguém for dono do que acontece com esse tempo.
10. Marque o que esta página não faz. Escopo de fora é parte do brief.

## Template

**Iniciativa:**

**Dono do resultado:**

### 1. Problema

Fricção medida:

Job to be done (quando / quero / para):

5 Porquês, se o pedido chegou como solução:

1.
2.
3.
4.
5.

### 2. Tarefa e rota

Tarefa (id do mapa):

Rota escolhida, e por que é a mais simples que resolve:

### 3. Quem usa, e onde no fluxo

### 4. Métrica

| | Linha de base | Alvo | Quando medir |
| :--- | :--- | :--- | :--- |
| Negócio | | | |
| Técnica (a que sustenta o alvo) | | | |

### 5. Autonomia desta versão

Decide sozinha:

Só recomenda:

Pessoa sempre decide:

### 6. Dados

| Dado | Onde está | Dono | Qualidade conhecida |
| :--- | :--- | :--- | :--- |
| | | | |

### 7. Riscos e salvaguardas

Ver [stakeholders e riscos](stakeholders-and-risks.md). Salvaguarda que esta versão já inclui:

### 8. Dono e critério de encerramento

Encerra se:

### Escopo

Faz:

Não faz:

### Retorno

Valor anual (premissas):

Custo total (construção + operação):

Tempo até o valor:

O que acontece com o tempo liberado, e quem garante:

## Exemplo preenchido — reembolso no Mercado Leme

**Iniciativa:** O2, recomendar aprovar ou recusar quando a política de uma página fecha.

**Dono do resultado:** Marina Costa, head de pós-venda.

### 1. Problema

990 dos 1.800 reembolsos mensais cabem numa regra já escrita, e mesmo assim esperam analista. O ciclo mediano até o dinheiro voltar é 2,4 dias, 80% disso em espera. A análise, quando começa, leva 18 minutos.

Job: quando a compradora pede reembolso dentro da política clara, o pós-venda quer uma recomendação conferível no mesmo dia, para o analista gastar o tempo nos 320 casos em que pedido, entrega e política não fecham.

5 Porquês a partir do pedido “quero um agente de reembolso”:

1. A fila leva 2,4 dias.
2. Todo caso espera analista, inclusive o que a política já resolve.
3. O fluxo não separa os casos da página de regras.
4. O id é copiado à mão e a política vive num documento, fora do chamado.
5. 990 casos por mês não pedem julgamento. Pedem a regra no fluxo.

### 2. Tarefa e rota

Tarefa O2. Rota: regra. O diagnóstico parou na pergunta 1. Modelo aqui acrescenta variação sem melhorar o acerto.

### 3. Quem usa, e onde no fluxo

O analista vê a recomendação dentro do chamado, com os campos que a regra leu (data, valor, primeira solicitação, status do lacre). A compradora não conversa com um bot nesta versão.

### 4. Métrica

| | Linha de base | Alvo | Quando medir |
| :--- | :--- | :--- | :--- |
| Negócio | 2,4 dias de ciclo mediano nos casos claros; 18 min de análise | Ciclo mediano de 1 dia nos casos claros; análise humana desses casos cai 80% | 8 semanas depois de ligar no fluxo |
| Técnica | Regra não está no fluxo | Em 200 casos rotulados antes de ligar, zero recomendação que discorde da política escrita | Antes do go-live, e amostra semanal depois |

### 5. Autonomia desta versão

Decide sozinha: nada que mova dinheiro.

Só recomenda: aprovar ou recusar, citando o item da política.

Pessoa sempre decide: o pagamento, qualquer valor acima de R$ 80, e qualquer exceção.

### 6. Dados

| Dado | Onde está | Dono | Qualidade |
| :--- | :--- | :--- | :--- |
| Pedido, data, valor, primeira solicitação | OMS | Operação de pedidos | Completo para os casos claros |
| Status de entrega e lacre | Rastreio | Operação de pedidos | Suficiente; falha de rastreio manda o caso para a pessoa |
| Texto do motivo | Helpdesk | Pós-venda | Não usado nesta versão |

### 7. Riscos e salvaguardas

Mapa em [stakeholders e riscos](stakeholders-and-risks.md). Nesta versão a salvaguarda é estrutural: a regra não dispara pagamento.

### 8. Dono e critério de encerramento

Marina Costa. Encerra se, em 8 semanas, a regra discordar dos analistas em mais de 5% dos casos claros. O aprendizado a registrar é qual item da política estava ambíguo. Não se “conserta” trocando a regra por um modelo.

### Escopo

Faz: localizar o pedido (O1 entra aqui), aplicar a política clara, gravar o motivo da recomendação, mostrar a evidência no chamado.

Não faz: pagar, classificar texto ambíguo (O3), investigar divergência (O4), decidir exceção (O5), responder a compradora em conversa aberta.

### Retorno

Valor: 237 horas por mês × R$ 45 × 12 = R$ 128 mil por ano, se Marina realocar essas horas para a fila de divergência. Sem esse redirecionamento, a conta cai pela metade.

Custo: 2 pessoa-mês para integrar e operar a regra no helpdesk. Custo de modelo: zero nesta versão.

Tempo até o valor: a primeira semana em que a recomendação aparece no chamado.

## O que este template não decide

Não desenha a jornada quadro a quadro nem a arquitetura. Também não autoriza sozinho a mudança de autonomia. Subir de “recomenda” para “paga” é outro brief, ou uma revisão explícita deste, com métrica e critério de encerramento novos.

## Segue para

[Stakeholders e riscos](stakeholders-and-risks.md), se o mapa ainda estiver rascunho. Com os dois fechados, o próximo tema é a experiência: storyboard e protótipo conceitual.
