# AI-RICE

Pontuação para ordenar candidatas que já passaram pelo diagnóstico e pela matriz. O alcance é a execução da tarefa, a confiança cai quando a evidência é fraca, e o esforço inclui operar — não só construir. A pontuação informa a fila. Não é a fila.

## Quando usar

- Há várias oportunidades qualificadas e uma capacidade só.
- A intuição e a pontuação estão em conflito, e alguém precisa mostrar a conta.

## Quando pular

- Sobrou uma candidata depois dos critérios eliminatórios. Registre a conta mesmo assim, para a revisão do mês seguinte.

## Antes de começar

- [Impacto × Viabilidade](impact-viability.md), já sem as linhas eliminadas.
- A rota de cada tarefa, vinda do [diagnóstico](task-diagnosis-matrix.md). Uma tarefa de julgamento disfarçada de tarefa cognitiva recebe confiança baixa.

## Passo a passo

1. Confirme de novo os eliminatórios: sem dado acessível ou sem dono, a linha não entra na tabela.
2. Alcance: quantas vezes por mês a tarefa acontece. Use a unidade do mapa, não “usuários” genéricos.
3. Impacto na escala fixa: 0,25 mínimo, 0,5 baixo, 1 médio, 2 alto, 3 massivo. Se tudo ficou em 3, refaça.
4. Confiança: evidência medida no processo vale 80% ou mais; referência de mercado, 50%; intuição de especialista, 30%. Ajuste para baixo se a rota do diagnóstico estiver incerta.
5. Esforço em pessoa-mês, somando construção, integração, avaliação de qualidade, operação e manutenção. Em agente, operação costuma passar a construção.
6. Pontuação = alcance × impacto × confiança ÷ esforço. Compare as linhas entre si. O número absoluto não significa nada sozinho.
7. Monte a fila Agora / Em seguida / Mais tarde. Afaste-se da ordem da pontuação só por um destes motivos, escrito: dependência de dado, credibilidade do programa ou aprendizado que a próxima iniciativa reutiliza.
8. Use custo do atraso só para desempate ou para uma urgência que a pontuação não vê (prazo que fecha, incidente, habilitador que destrava as outras). Some valor de negócio, criticidade de tempo e redução de risco, e divida pela duração. Escreva o desempate em uma frase.

### Agora / Em seguida / Mais tarde

| Coluna | O que vive ali |
| :--- | :--- |
| Agora | Em execução, com gente alocada e métrica definida. Sem data prometida que o aprendizado ainda não sustenta |
| Em seguida | Comprometida em intenção. Espera capacidade ou dependência |
| Mais tarde | Aposta qualificada, visível, sem prazo cobrado |

A cada revisão, o item muda de coluna com a justificativa registrada. A pergunta útil para quem espera é: o que precisa ser verdade para isto subir de coluna?

## Template

**Capacidade desta rodada** (pessoa-mês):

| Id | Alcance (exec./mês) | Impacto (0,25–3) | Confiança | Esforço (pessoa-mês) | Pontuação | Por quê a confiança é esta |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | | | | | |
| | | | | | | |

**Custo do atraso** (só onde desempatou ou mudou a ordem):

| Coluna | Ids | Por que esta coluna, se a ordem não for a da pontuação |
| :--- | :--- | :--- |
| Agora | | |
| Em seguida | | |
| Mais tarde | | |

## Exemplo preenchido — reembolso no Mercado Leme

Capacidade da rodada: 4 pessoa-mês. O1 (integração do id) entra no esforço de O2, não como linha própria.

| Id | Alcance | Impacto | Confiança | Esforço | Pontuação | Confiança |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| O2 Regra da política | 990 | 2 | 80% | 2 | 792 | Volume medido no OMS e regra já escrita |
| O3 Classificar motivo | 1.800 | 1 | 70% | 2,5 | 504 | Texto existe; rótulo só em 70% do log |
| O4 Agente de divergência | 320 | 3 | 50% | 5 | 96 | Caminho variável ainda sem amostra rotulada de ponta a ponta |
| O5 Resumo de exceção | 90 | 1 | 80% | 1 | 72 | Casos reais desta fila, escopo pequeno |

Conta de O2: 990 × 2 × 0,8 ÷ 2 = 792. O4 fica atrás mesmo com impacto 3, porque alcança menos casos, com menos evidência e com o triplo do esforço.

| Coluna | Ids | Justificativa |
| :--- | :--- | :--- |
| Agora | O2 | Maior pontuação, e a integração do id é o habilitador. Não promete data de pagamento automático: nesta coluna a regra só recomenda |
| Em seguida | O3 | Segunda pontuação. Sobe junto se o jurídico fechar o prazo dos códigos de motivo; hoje esse prazo não existe, então não fura a fila |
| Mais tarde | O4, depois O5 | O4 depende do log de decisão que O2 passa a gravar. O5 é pequeno e útil, e não ocupa a capacidade de O2 |

Custo do atraso não mudou a ordem. Ficou registrado para a revisão: se o código de motivo virar obrigação em 90 dias, O3 empata com O2 pelo prazo e os dois dividem o Agora.

## O que este template não decide

Não escreve o problema, a métrica de sucesso nem o critério para encerrar. A primeira da fila ainda precisa de uma página que qualquer pessoa leia em cinco minutos.

## Segue para

[Brief de caso de uso](../use-case/brief.md) da iniciativa que ficou no Agora, e o [mapa de stakeholders e riscos](../use-case/stakeholders-and-risks.md) dessa mesma iniciativa.
