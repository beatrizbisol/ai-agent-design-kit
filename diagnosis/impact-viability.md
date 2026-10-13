# Matriz Impacto × Viabilidade

Uma nota de 1 a 5 em dois eixos para decidir o que merece ser construído. A viabilidade é a pior dimensão, não a média. Risco não é um terceiro eixo: ele reduz o impacto, reduz a viabilidade ou tira a oportunidade da matriz.

## Quando usar

- As tarefas já têm rota na matriz de diagnóstico.
- Há mais candidatas do que capacidade, e a conversa está em “qual a gente faz”.

## Quando pular

- Existe uma única candidata já comprometida por obrigação externa (prazo regulatório, incidente). Mesmo assim, registre a nota para não perder a comparação na rodada seguinte.

## Antes de começar

- [Diagnóstico de tarefas](task-diagnosis-matrix.md) e a fricção medida no [mapa](../discovery/opportunity-map.md).
- Na mesma conversa: quem executa, quem é dono do resultado e quem entende dos dados. Nota dada sozinho esconde premissa.

## Passo a passo

1. Risque o que é eliminatório antes de notar: sem dados que alguém consiga mostrar, sem dono do resultado, ou risco regulatório sem desenho de controle. Isso vai para “reavaliar”, não para o quadrante.
2. Estime o impacto a partir da fricção, não da tecnologia: volume × custo unitário × taxa realista de automação. Declare cada premissa. Nunca use 100% de automação.
3. Pergunte o que será feito com o tempo liberado e quem garante isso. Sem resposta, corte a estimativa pela metade.
4. Note a viabilidade em quatro dimensões, de 1 a 5. A nota do eixo é a menor das quatro.
5. Deixe o risco redesenhar a solução: sugerir, executar com auditoria, ou executar só dentro de uma alçada. A versão com pessoa no circuito entrega menos economia e custa mais controle. Anote qual versão você notou.
6. Leia o quadrante. Não aprove dez pilotos porque vários caíram no canto certo.

### Impacto (1 a 5)

| Nota | Leitura |
| :--- | :--- |
| 1 | Quase não move custo, tempo ou receita |
| 2 | Ganho local, fácil de absorver sem mudar o fluxo |
| 3 | Ganho claro num time, ainda sem efeito no indicador da área |
| 4 | Move tempo de ciclo, erro ou capacidade do processo |
| 5 | Move o indicador que a diretoria já acompanha |

Moedas aceitas: financeira (custo, receita, capital), operacional (ciclo, qualidade, capacidade) e estratégica. Estratégica sozinha, sem conta, não passa de 3.

### Viabilidade (1 a 5 em cada dimensão)

| Dimensão | 1 | 5 |
| :--- | :--- | :--- |
| Dados | Ninguém mostra uma amostra em uma semana | Amostra acessível, com qualidade conhecida e permissão de uso |
| Complexidade | Agente com vários sistemas, erro caro, pouca previsibilidade | Regra estável ou IA pontual já compreendida |
| Integração | Tela antiga ou planilha solta, fora do fluxo de quem trabalha | API e encaixe no fluxo real |
| Pessoas | Sem dono, ou resistência não endereçada | Dono nomeado e quem executa participa |

A rota do diagnóstico calibra complexidade: regra é mais viável que IA pontual, que é mais viável que agente. Some o custo de operar, monitorar e retreinar. Construção sozinha subestima o denominador.

### Quadrantes

| | Viabilidade alta (4–5) | Viabilidade baixa (1–2) |
| :--- | :--- | :--- |
| Impacto alto (4–5) | Vitória rápida. Primeira entrega | Aposta estratégica. Investir em dado ou integração antes de construir |
| Impacto baixo (1–2) | Melhoria oportunista. Só se sobrar capacidade | Descarte |

Nota 3 fica na fronteira: escreva por que você arredondou para um lado. Risco alto no mesmo quadrante não é a mesma decisão — anote o nível de autonomia assumido na nota.

## Template

**Processo:**

**Quem notou (operação, dono, dados):**

| Id | Tarefa e rota | Conta de impacto | Impacto (1–5) | Dados | Complexidade | Integração | Pessoas | Viabilidade (mínimo) | Quadrante | Autonomia assumida na nota |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | | | | | | | | | |
| | | | | | | | | | | |

**Eliminadas antes da matriz:**

**Premissas:**

**O que entra, o que espera, o que sai:**

## Exemplo preenchido — reembolso no Mercado Leme

Notaram Marina Costa, um analista e a pessoa de dados do helpdesk. Hora do analista: R$ 45. Premissa: observação de 40 casos numa semana.

| Id | Tarefa e rota | Conta de impacto | Imp. | Dados | Compl. | Integr. | Pessoas | Viab. | Quadrante | Autonomia na nota |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| O2 | Regra da política clara | 990 casos × 18 min × 80% = 237 h/mês. Marina usa as horas para a fila de divergência, sem contratação nova | 4 | 5 | 5 | 4 | 4 | 4 | Vitória rápida | Só recomenda. Não paga |
| O3 | IA pontual de classificação | 1.800 × 6 min × 70% = 126 h/mês, se o rótulo entrar no fluxo em vez de uma tela à parte | 4 | 4 | 4 | 4 | 4 | 4 | Vitória rápida | Rótulo automático com amostra; ambíguo passa sem rótulo |
| O4 | Agente de divergência | 320 × 45 min × 50% = 120 h/mês, mais parte dos R$ 70 de erro. Depende de log melhor | 5 | 2 | 2 | 3 | 3 | 2 | Aposta estratégica | Pesquisa e recomenda. Não paga |
| O5 | Resumo para a exceção humana | 90 casos. A decisão continua humana; o ganho é a coleta | 2 | 4 | 4 | 4 | 5 | 4 | Melhoria oportunista | Rascunho. Pessoa decide |
| O1 | Integração do id | Incluso na conta de O2. Sozinho não move o ciclo | 2 | 5 | 5 | 4 | 4 | 4 | Melhoria oportunista | Determinístico |

**Eliminada:** recusar pelo tom da mensagem. Sem política e com risco reputacional.

**Decisão desta rodada:** construir O2 e O3. O1 entra junto de O2 porque é a integração que a regra precisa. O4 espera dado de decisão mais completo. O5 não ocupa o lugar de O2.

## O que este template não decide

Não define a sequência semana a semana. Duas vitórias rápidas ainda disputam a mesma capacidade. A ordem é o próximo arquivo.

## Segue para

[AI-RICE](ai-rice.md), só com as linhas que não foram eliminadas.
