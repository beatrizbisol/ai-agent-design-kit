# Stakeholders e riscos

Quem pode aprovar, atrasar ou vetar a iniciativa, e o que fazer quando o sistema errar. O brief aponta para este mapa. Os dois andam juntos porque autonomia sem dono de risco é só uma frase.

## Quando usar

- O brief já tem uma rota e um nível de autonomia, mesmo em rascunho.
- Jurídico, privacidade ou a área usuária ainda não viram a iniciativa, e o risco de veto tardio é real.

## Quando pular

- A iniciativa não toca dado pessoal, dinheiro, decisão sobre pessoa ou marca, e o dono do resultado já está nomeado. Mesmo assim, faça a RACI de uma linha. O pulo completo quase nunca se sustenta em agente que age no fluxo.

## Antes de começar

- [Brief](brief.md) com escopo de dentro e de fora.
- Os nomes das pessoas, não só das áreas. “O jurídico” não comparece a uma reunião.

## Passo a passo

1. Liste quem ganha, quem perde tempo, quem assina o orçamento e quem pode vetar.
2. Posicione cada um em poder e interesse. Alto poder e baixo interesse (privacidade, jurídico, segurança) entra cedo, antes de o desenho fechar.
3. Preencha a RACI. Uma pessoa é accountable — a mesma dona do resultado no brief. Responsável executa. Consultado opina antes da decisão. Informado recebe o que mudou.
4. Abra uma linha de risco por modo de falha que muda a autonomia: resposta inventada, dado pessoal exposto, decisão enviesada. Some outros modos se o processo tiver (pagamento duplicado, ação irreversível).
5. Note probabilidade e severidade em baixo, médio ou alto. Severidade alta com controle inexistente volta para o brief e reduz a autonomia.
6. Para cada risco alto, escreva o ciclo: detectar, interromper, avaliar, recuperar. Interromper inclui quem pode desligar a iniciativa no mesmo dia.
7. Leve o mapa para os consultados antes de tratar o brief como aprovado.

## Template

**Iniciativa (a mesma do brief):**

### Poder × interesse

| Pessoa | Papel | Poder | Interesse | O que precisa dela antes de construir |
| :--- | :--- | :--- | :--- | :--- |
| | | alto / médio / baixo | alto / médio / baixo | |

### RACI

| Atividade | Responsible | Accountable | Consulted | Informed |
| :--- | :--- | :--- | :--- | :--- |
| Desenho da solução | | | | |
| Aprovação para ligar no fluxo | | | | |
| Operação e qualidade | | | | |
| Desligar se o critério de encerramento disparar | | | | |

### Riscos

| Risco | Como acontece neste processo | Prob. | Sev. | Salvaguarda nesta versão | Detectar | Interromper | Avaliar | Recuperar |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Resposta sem fundamento na fonte | | | | | | | | |
| Dado pessoal a mais no contexto ou no log | | | | | | | | |
| Decisão desigual entre grupos parecidos | | | | | | | | |
| | | | | | | | | |

**Quem pode desligar no mesmo dia:**

## Exemplo preenchido — reembolso no Mercado Leme

Iniciativa O2, regra que recomenda e não paga.

### Poder × interesse

| Pessoa | Papel | Poder | Interesse | Antes de construir |
| :--- | :--- | :--- | :--- | :--- |
| Marina Costa | Dona do resultado | alto | alto | Aceite da métrica e do critério de encerramento |
| Analistas de reembolso | Quem confirma a recomendação | baixo | alto | Participar da rotulagem dos 200 casos |
| Financeiro | Caixa do reembolso | alto | médio | Confirmar que pagamento continua na fila humana |
| DPO | Privacidade | alto | baixo | Ver quais campos entram no log |
| Jurídico | Política de arrependimento | alto | baixo | Confirmar que a página de regras está vigente |
| Lojista | Sofre o débito lá na frente | baixo | médio | Só informar. Esta versão não muda o débito |

### RACI

| Atividade | Responsible | Accountable | Consulted | Informed |
| :--- | :--- | :--- | :--- | :--- |
| Desenho da solução | Engenharia do helpdesk | Marina Costa | DPO, jurídico, analistas | Financeiro |
| Aprovação para ligar no fluxo | Marina Costa | Marina Costa | Jurídico, financeiro | Analistas |
| Operação e qualidade | Pós-venda + engenharia | Marina Costa | DPO | Financeiro |
| Desligar se o critério disparar | Engenharia, no mesmo dia em que Marina pedir | Marina Costa | Jurídico | Analistas e financeiro |

### Riscos

| Risco | Como acontece | Prob. | Sev. | Salvaguarda | Detectar | Interromper | Avaliar | Recuperar |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Resposta sem fundamento | Baixo nesta versão: a saída cita o campo lido. Sobe se alguém trocar a regra por texto livre | baixa | alta | Só recomenda, citando data, valor e item da política | Amostra semanal contra o analista | Marina pede para tirar a recomendação do chamado | Comparar os casos discordantes com a página de regras | Corrigir a regra. Não “cobrir” com um modelo |
| Dado pessoal a mais | Log guarda CPF ou dado de cartão que o chamado nem precisava | média | alta | Log só com id do pedido, campos da regra e id de quem confirmou | Revisão do DPO no esquema do log, antes de ligar | Parar o log novo | Ver o que já foi gravado | Apagar o campo excedente e registrar o incidente |
| Decisão desigual | A regra usa um proxy que pega mais um grupo de compradores | baixa | alta | A regra só usa data, valor, primeira vez e lacre. Sem texto e sem dado demográfico | Recorte da taxa de recusa por região e canal, mensal | Pausar o item da regra que causar o recorte | Jurídico e Marina leem o recorte | Ajustar a política escrita antes de religar |
| Pagamento duplicado ou indevido | Fora do escopo enquanto a pessoa paga. Vira risco real se a autonomia subir | baixa agora | alta | Pagamento não está nesta versão | Fila de pagamento segue como hoje | Não há o que desligar no pagamento | — | — |

**Quem desliga no mesmo dia:** Marina decide, engenharia tira a recomendação do fluxo.

## O que este template não decide

Não prioriza o portfólio e não desenha a tela. Se a salvaguarda e a autonomia do brief discordarem, o brief é que se reescreve.

## Segue para

[Storyboard](../experience/storyboard.md) da mesma iniciativa.
