# Roadmap de 3 horizontes

Como uma mesma solução cresce de autonomia. O primeiro horizonte é estreito na tarefa e rigoroso no controle. O salto de horizonte só acontece com critério escrito, não quando o time “se sentir pronto”.

## Quando usar

- O [protótipo conceitual](../experience/conceptual-prototype.md) descreve a versão atual.
- Alguém quer pagamento automático, mais canais ou um agente de ponta a ponta antes de a versão atual ter métrica.

## Quando pular

- A iniciativa é um experimento de uma semana, sem intenção de operar no fluxo. Nesse caso, o brief e o critério de encerramento bastam.

## Antes de começar

- [Brief](../use-case/brief.md), com métrica e critério de encerramento.
- A fila do [AI-RICE](../diagnosis/ai-rice.md). Horizonte não é licença para puxar a aposta estratégica para o primeiro mês.

## Passo a passo

1. Escreva o horizonte 1 como a versão já especificada no protótipo. Se o horizonte 1 faz mais do que o protótipo, o protótipo é que está atrasado.
2. Liste o que essa versão já precisa ter no primeiro dia no fluxo: registro do que foi lido, forma de desligar no mesmo dia, silêncio quando falta dado, e pessoa no ponto que o brief marcou.
3. Coloque cada iniciativa do AI-RICE num horizonte. Agora tende ao horizonte 1. Aposta estratégica tende ao 3, salvo se o dado que ela precisa é justamente o que o horizonte 1 passa a gravar.
4. Suba a escada de autonomia um degrau por vez: lê e organiza, recomenda, executa sob supervisão, decide sozinha num nicho delimitado. Pular degrau exige um brief novo.
5. Escreva o critério de passagem. Número, janela de tempo e quem confere. Sem isso, o horizonte 2 começa por entusiasmo.
6. No horizonte 3, diga se muda o modelo de operação ou se muda o que a empresa vende. Se não muda nenhum dos dois, o horizonte 3 ainda é expansão, e o nome deve dizer isso.
7. Revise as datas como janelas, não como compromisso externo. A qualidade sobre o dado real só aparece depois dos primeiros casos.

### Escada de autonomia

| Degrau | A solução | A pessoa |
| :--- | :--- | :--- |
| Lê | Organiza e cita a fonte | Decide e executa |
| Recomenda | Propõe uma ação com a evidência | Confirma ou descarta |
| Executa sob supervisão | Age dentro de uma alçada | Audita amostra e pega a exceção |
| Decide num nicho | Age sozinha num recorte em que o erro é barato e reversível | Define o nicho e pode desligar |

## Template

**Iniciativa-mãe:**

**Degrau de autonomia hoje:**

| Horizonte | Janela | O que entra | O que fica de fora | Degrau | Métrica de sucesso | Critério para passar ao próximo |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1. Eficiência no escopo estreito | | | | | | |
| 2. Expansão de capacidade | | | | | | |
| 3. Mudança de operação ou de oferta | | | | | | |

**Já no primeiro dia do horizonte 1**

- [ ] Registro do que foi lido e da versão da regra ou do critério
- [ ] Alguém desliga no mesmo dia
- [ ] Dado que falta não é completado por suposição
- [ ] O ponto humano do brief existe no fluxo, não num documento
- [ ] Log sem dado pessoal além do que o [mapa de riscos](../use-case/stakeholders-and-risks.md) autorizou

**O que o horizonte 1 deixa de herança para o seguinte:**

## Exemplo preenchido — reembolso no Mercado Leme

**Iniciativa-mãe:** reembolso do comprador. A versão em construção é O2.

**Degrau hoje:** nenhum. O analista faz tudo.

| Horizonte | Janela | O que entra | Fora | Degrau | Métrica | Passagem |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0–3 meses | O2: localizar pedido e recomendar quando a política clara fecha | Pagamento, texto livre, divergência, exceção | Recomenda | Ciclo mediano dos casos claros em 1 dia; discordância com analista ≤ 5% em 8 semanas; zero recomendação fora da política nos 200 casos prévios | Marina e jurídico conferem a amostra. DPO já viu o log. Aí sim discute-se execução |
| 2 | 3–9 meses | Pagamento automático só até R$ 80, quando a regra fecha, com auditoria de 10%. O3, classificar o motivo, entra se o log do horizonte 1 tiver rótulo utilizável | Divergência (O4) e exceção (O5) | Executa sob supervisão, no nicho da política clara | Reembolso indevido ≤ 1% no trimestre; ciclo mediano segue ≤ 1 dia | Um trimestre dentro da meta de erro, com a auditoria de 10% feita de verdade |
| 3 | 9–24 meses | O4: investigar pedido, entrega e política, ainda sem pagar e sem decidir exceção. O posto do analista passa a ser a exceção e a amostra | Julgamento de lojista estratégico continua humano | Recomenda no caso difícil; executa só no nicho já provado no horizonte 2 | 60% dos 320 casos de divergência fechados sem a pesquisa manual | Não é oferta nova. É mudança de operação: analista deixa de ser a primeira leitura dos casos claros |

**Herança do horizonte 1:** log de decisão com os campos da regra, a versão da política e o id de quem confirmou. Sem esse log, o horizonte 2 não tem o que auditar e o O4 não tem o que aprender.

## O que este template não decide

Não escolhe topologia, memória nem modelo. Também não antecipa o horizonte 2 no código do horizonte 1, além do registro e do desligamento que a passagem vai precisar.

## Segue para

Arquitetura da versão do horizonte 1: [topologia](../architecture/orchestration-topology.md), [memória](../architecture/memory.md), [ação e supervisão](../architecture/action-and-supervision.md) e [escolha do motor](../architecture/reasoning-engine.md).
