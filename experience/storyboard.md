# Storyboard do agente

A jornada em quadros, antes de interface e de código. Cada quadro diz o contexto, a intenção, a decisão e o controle humano. Um quadro bom é específico o bastante para implementar e simples o bastante para negócio, engenharia e operação discutirem juntos.

## Quando usar

- O [brief](../use-case/brief.md) já fixou tarefa, rota e autonomia.
- O time ainda descreve a solução como “vai ter IA” e ninguém consegue dizer o que acontece no caso concreto.

## Quando pular

- A jornada desta versão já está em quadros que uma pessoa de fora explica em um minuto, incluindo o ponto em que uma pessoa assume.

## Antes de começar

- Brief com escopo de dentro e de fora, e [stakeholders e riscos](../use-case/stakeholders-and-risks.md).
- Um caso real, não um caso médio. O caso médio esconde a exceção.

## Passo a passo

1. Escreva no cabeçalho a hipótese e o papel. Papel é um destes: orientar, responder, recomendar, automatizar, acionar. Se precisar de três papéis, são três jornadas.
2. Hipótese no formato: se [papel] ajudar [quem] em [momento], esperamos [resultado], medido por [métrica], com [controle humano].
3. Desenhe de quatro a sete quadros. Cada um responde: onde estamos, o que a pessoa quer, o que a solução decide, o que precisa de validação.
4. Inclua pelo menos um quadro em que a solução para e uma pessoa segue. Sem esse quadro, a autonomia do brief não está na jornada.
5. Mostre também o caso que não entra no escopo, num quadro curto de saída. O leitor precisa ver a solução recusar, não só acertar.
6. Leia a sequência para alguém que não participou. Se essa pessoa não repetir a jornada em um minuto, o quadro ainda está abstrato.
7. Não ilustre tela. Mensagem, campo e estado visual são o protótipo seguinte, se você precisar deles.

## Template

**Iniciativa:**

**Hipótese:** se ________ ajudar ________ em ________, esperamos ________, medido por ________, com ________.

**Papel nesta versão:** orientar / responder / recomendar / automatizar / acionar

**Quem mais aparece:**

| # | Contexto | Intenção | Decisão | Controle |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Onde, quem, canal | O que a pessoa quer resolver | Perguntar, responder, recomendar, executar ou recusar | O que valida, aprova ou assume |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |

**Quadro de saída (fora do escopo):**

**O que uma pessoa de fora repetiu, em uma frase:**

## Exemplo preenchido — reembolso no Mercado Leme

**Iniciativa:** O2.

**Hipótese:** se uma recomendação por regra ajudar o analista no momento em que ele abre o chamado claro, esperamos o ciclo mediano desses casos em 1 dia e 80% menos minutos de análise, medido em 8 semanas, com pagamento sempre confirmado por uma pessoa.

**Papel nesta versão:** recomendar. Não automatiza o pagamento e não responde à compradora.

**Quem mais aparece:** compradora (só como origem do chamado), analista, fila de pagamento.

| # | Contexto | Intenção | Decisão | Controle |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Compradora pede reembolso no app. Pedido entregue há 3 dias, R$ 64, primeira solicitação | “Veio amassado, quero o dinheiro de volta” | O fluxo não lê o texto para decidir. Abre o chamado para o analista com os campos da regra | Nenhum ainda |
| 2 | Analista abre o chamado no helpdesk | Saber se a política clara fecha, sem copiar o id para o OMS | A integração localiza pedido e entrega. A regra confere data, valor, primeira vez e entrega. Recomenda aprovar e cita o item da política | Analista vê os quatro campos. Se um falta, não há recomendação |
| 3 | Os quatro campos fecham | Analista quer seguir sem reler a política inteira | A recomendação fica no chamado: aprovar, com a evidência ao lado | Analista confirma ou descarta. Só a confirmação segue para a fila de pagamento, que continua humana |
| 4 | O caso não fecha a regra: valor acima de R$ 80, entrega sem status, ou lojista marcado como exceção | Analista não deve ganhar uma recomendação falsa | Nenhuma recomendação. O chamado permanece na fila atual | A pessoa segue o processo de hoje. Exceção não é decidida aqui |

**Quadro de saída:** a compradora escreve um motivo ambíguo e a entrega não confirma o lacre. O quadro 4 se aplica. Classificar o texto é outra iniciativa (O3), com outro storyboard.

**Frase de fora:** “Quando a regra fecha, o analista vê uma recomendação com a evidência e confirma; o dinheiro não sai sozinho. Quando a regra não fecha, o sistema fica quieto.”

## O que este template não decide

Não define entradas, saídas e limites com o detalhe de implementação. Também não promove a autonomia: o quadro 3 não vira pagamento automático sem outro brief.

## Segue para

[Protótipo conceitual](conceptual-prototype.md) da mesma jornada.
