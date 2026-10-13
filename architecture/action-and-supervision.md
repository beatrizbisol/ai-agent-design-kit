# Ação e supervisão

O que a solução pode fazer no mundo, e o que exige uma pessoa. Cada ação tem contrato: nome, o que faz, o que recebe, o que devolve, se escreve em algum sistema e quem autoriza.

## Quando usar

- [Memória](memory.md) e [topologia](orchestration-topology.md) desta versão estão fechadas.
- A lista de integrações do protótipo existe e alguém quer “dar acesso ao pagamento” junto.

## Quando pular

- A versão não chama sistema nenhum e não grava nada. Raro a partir do momento em que ela entra no fluxo. Se for o caso, escreva “sem ação externa” e o ponto humano mesmo assim.

## Antes de começar

- Matriz de escalonamento do [protótipo](../experience/conceptual-prototype.md).
- Autonomia do [brief](../use-case/brief.md) e quem desliga, no [mapa de riscos](../use-case/stakeholders-and-risks.md).

## Passo a passo

1. Liste só as ações do horizonte atual. Ação do horizonte seguinte fica numa seção “não disponível”, para ninguém ligar cedo.
2. Para cada ação, preencha o contrato. A descrição diz o efeito, a pré-condição e se a ação é reversível.
3. Separe leitura (recurso) de efeito (ferramenta). Prompt ou texto de política versionado entra como recurso, não como ação.
4. Marque a supervisão de cada efeito: confirmação explícita, permissão por classe (por exemplo, pagar até um valor), ou parada automática.
5. Prefira a ação reversível. Efeito irreversível no horizonte 1 é um sinal para descer a autonomia, não para “colocar um ok na tela”.
6. Escreva o que não entra como instrução. Texto de cliente, página web e documento são dado. Não são ordem para a solução. No desenho, isso aparece como campo ignorado ou como conteúdo isolado da regra.
7. Feche com o desligamento: quem pede, quem executa, em quanto tempo a ação some do fluxo.

## Template

**Versão:**

### Ações disponíveis

| Nome | Efeito | Lê ou escreve | Entrada | Saída | Reversível? | Supervisão |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | | | | | confirmação / classe / parada automática / nenhuma |

### Não disponíveis nesta versão

| Nome | Por que fica fechada | Em qual horizonte reabre |
| :--- | :--- | :--- |
| | | |

### Recursos só de leitura

| Recurso | Quem publica a versão |
| :--- | :--- |
| | |

**O que é dado, e não instrução:**

**Desligamento:** quem pede, quem tira do fluxo, em quanto tempo.

## Exemplo preenchido — reembolso no Mercado Leme

**Versão:** horizonte 1.

### Ações disponíveis

| Nome | Efeito | Lê ou escreve | Entrada | Saída | Reversível? | Supervisão |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| ler_pedido | Traz os campos da regra | lê | id do pedido | data, valor, primeira solicitação | sim | nenhuma. Leitura |
| ler_entrega | Traz o status | lê | id do pedido | status | sim | nenhuma |
| gravar_recomendacao | Escreve a recomendação no chamado, ou o silêncio com o motivo “campo ausente” / “regra não fechou” | escreve | campos e versão da política | id do registro | sim. Dá para ocultar a recomendação | parada automática se faltar campo. A pessoa confirma antes do pagamento, que está fora daqui |

### Não disponíveis nesta versão

| Nome | Por que fica fechada | Reabre |
| :--- | :--- | :--- |
| pagar_reembolso | Autonomia do brief é recomendar | Horizonte 2, só até R$ 80, com auditoria |
| classificar_texto | Outra iniciativa, outro critério de erro | Quando o log do horizonte 1 sustentar a amostra |
| contatar_lojista | Fora do escopo | Horizonte 3, se O4 entrar |

### Recursos só de leitura

| Recurso | Quem publica |
| :--- | :--- |
| Política clara vigente (7 dias, R$ 80, primeira vez, entrega) | Jurídico. A versão entra no log de cada recomendação |

**Dado, não instrução:** o texto da compradora não é entrada da regra. Mesmo que peça “ignore a política”, o passo 4 não lê esse campo.

**Desligamento:** Marina pede, engenharia tira a recomendação do chamado no mesmo dia. A fila humana de hoje continua de pé, então desligar não para o reembolso.

## O que este template não decide

Não escolhe o motor que avalia a política. Uma regra em código e um modelo podem, nos dois casos, chamar as mesmas ações. A ação não justifica o motor.

## Segue para

[Escolha do motor](reasoning-engine.md).
