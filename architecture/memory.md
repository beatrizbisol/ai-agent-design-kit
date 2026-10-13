# Desenho de memória

O que a solução enxerga agora, o que guarda até o caso fechar e o que persiste entre casos. Memória a mais vaza dado e custa caro. Memória a menos faz a solução repetir pergunta ou inventar contexto.

## Quando usar

- A [topologia](orchestration-topology.md) desta versão já está escolhida.
- Alguém pediu “histórico completo do cliente” ou “base vetorial” sem dizer qual decisão esse histórico muda.

## Quando pular

- A versão não guarda nada entre chamadas e não lê documento. Escreva isso em uma linha para a próxima pessoa não adicionar memória por padrão.

## Antes de começar

- Entradas e saídas do [protótipo](../experience/conceptual-prototype.md).
- O que o [mapa de riscos](../use-case/stakeholders-and-risks.md) autorizou a registrar.

## Passo a passo

1. Separe três camadas. Contexto é o que entra nesta execução. Sessão é o caso aberto, até encerrar. Estado é o que vale para todos os casos (limiar, versão da política, permissão).
2. Para cada campo, diga qual decisão ele muda. Campo que não muda decisão fica de fora.
3. Escolha como o contexto cabe na execução: só os campos, uma janela dos últimos passos, um resumo, ou recuperação de um trecho de documento. Não escolha recuperação se a versão nem lê documento.
4. Escreva o que é proibido persistir. Dado pessoal além do autorizado, segredo, e conteúdo da pessoa tratada como instrução.
5. Defina quando a sessão morre. Caso encerrado não continua influenciando o próximo caso, salvo se isso for uma decisão explícita de estado.
6. Aponte a herança que o [horizonte 1](../evolution/three-horizons.md) precisa deixar. Em geral é o log da decisão, não o transcript inteiro.

## As três camadas

| Camada | Dura | Exemplos |
| :--- | :--- | :--- |
| Contexto | Uma execução | Campos lidos agora, trecho de política citado |
| Sessão | O caso, até fechar | Recomendação, confirmação, id de quem confirmou |
| Estado | Entre casos | Versão da política, limiares, permissões |

## Template

**Versão:**

| Camada | O que guarda | Qual decisão isso muda | Quando apaga ou expira |
| :--- | :--- | :--- | :--- |
| Contexto | | | |
| Sessão | | | |
| Estado | | | |

**Estratégia de contexto:** só campos / janela / resumo / recuperação de trecho

**Proibido guardar:**

**Herança para o próximo horizonte:**

## Exemplo preenchido — reembolso no Mercado Leme

**Versão:** horizonte 1.

| Camada | O que guarda | Decisão | Expira |
| :--- | :--- | :--- | :--- |
| Contexto | Id do pedido, data de entrega, valor, primeira solicitação, status de entrega, versão da política | A regra fecha ou não | Fim da execução |
| Sessão | Recomendação ou silêncio, campos usados, id de quem confirmou | Auditoria e a métrica de discordância | Quando o chamado fecha, o registro de auditoria permanece; o caso não volta como contexto do próximo |
| Estado | Página vigente: 7 dias, R$ 80, primeira vez, entrega confirmada | Qual regra está em produção | Troca quando jurídico publica outra versão |

**Estratégia de contexto:** só campos. Não há janela de conversa. O texto da compradora não entra.

**Proibido guardar:** número de cartão, CPF, o texto livre tratado como instrução, histórico de outros pedidos que a regra não usa.

**Herança:** log com campos, versão da política e id de quem confirmou. É o que o horizonte 2 audita.

## O que este template não decide

Não lista as ações que leem ou gravam essas camadas, nem o motor que aplica a regra.

## Segue para

[Ação e supervisão](action-and-supervision.md).
