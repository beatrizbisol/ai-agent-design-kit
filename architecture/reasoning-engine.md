# Escolha do motor

Qual mecanismo executa a decisão desta versão: regra, modelo pequeno, modelo grande ou modelo de raciocínio. A rota do diagnóstico manda. O nome do fornecedor não.

## Quando usar

- [Ação e supervisão](action-and-supervision.md) já listam o que esta versão pode fazer.
- A conversa chegou em “qual modelo” antes de separar regra de interpretação.

## Quando pular

- O diagnóstico fechou em regra e ninguém está propondo modelo. Registre “regra” numa linha para a decisão não ser reaberta por omissão.

## Antes de começar

- Rota na [matriz de diagnóstico](../diagnosis/task-diagnosis-matrix.md).
- Métrica técnica do [brief](../use-case/brief.md). O motor precisa ser avaliável por essa métrica.

## Passo a passo

1. Volte à rota. Se a pergunta 1 do diagnóstico foi sim, o motor é regra ou código. Pare aqui para essa tarefa.
2. Se a tarefa é estreita, estruturada e já tem exemplos rotulados, compare uma regra e um modelo clássico pequeno antes de um modelo grande. Interpretável e barato ganha quando acerta o bastante.
3. Use modelo grande quando a matéria é texto ou documento e a regra não fecha, e a saída é uma classe, uma extração ou um rascunho conferível.
4. Use modelo de raciocínio quando o caminho varia, há vários passos de planejamento e um modelo que responde direto não sustenta a métrica. Isso é exceção no horizonte 1.
5. Se a versão mistura tarefas, cada tarefa pode ter um motor. Não coloque um modelo grande na frente de uma regra que já fecha.
6. Escreva como a métrica técnica será medida: conjunto rotulado, amostra, ou conferência humana. Motor sem avaliação não entra no fluxo.
7. Anote custo de execução só se houver modelo. Regra em código não herda orçamento de token “por precaução”.

## Quando cada motor cabe

| Motor | Cabe | Não cabe |
| :--- | :--- | :--- |
| Regra ou código | A mesma entrada produz a mesma saída e a política cabe escrita | Texto ambíguo, caminho que muda a cada caso |
| Modelo pequeno ou clássico | Tarefa estreita, dado estruturado ou rótulo suficiente, custo e latência apertados | Texto longo sem exemplo rotulado |
| Modelo grande | Interpretar, classificar, extrair ou rascunhar linguagem, com revisão do erro | Decisão que uma página de regras já resolve |
| Modelo de raciocínio | Planejar vários passos em que a tentativa única erra a métrica | Horizonte 1, fluxo auditável, ou tarefa de um passo |

## Template

**Versão:**

| Tarefa | Rota do diagnóstico | Motor | Como a métrica técnica é medida | Custo de execução que importa |
| :--- | :--- | :--- | :--- | :--- |
| | | | | |

**Motor que alguém pediu e ficou de fora, com o motivo:**

**O que faria esta escolha ser revista:**

## Exemplo preenchido — reembolso no Mercado Leme

**Versão:** horizonte 1, tarefa O2.

| Tarefa | Rota | Motor | Métrica | Custo |
| :--- | :--- | :--- | :--- | :--- |
| Aplicar a política clara | Regra | Código. Limiares versionados com a política | 200 casos rotulados antes de ligar: zero discordância da página. Depois, amostra semanal contra o analista | Nenhum token. O custo é a integração |

**Ficou de fora:** um modelo grande “para entender o motivo da compradora”. O texto não é entrada desta versão. Classificar o motivo é O3, no horizonte 2, e mesmo lá o primeiro candidato é um classificador avaliado por amostra, não um modelo de raciocínio. O4, se um dia entrar, reabre esta tabela. Não reabre a de O2.

**Revisão:** se a página de regras deixar de caber numa página, ou se duas pessoas divergirem nos mesmos vinte casos claros, a rota deixa de ser regra. Aí o brief se reescreve. Não se troca o motor em silêncio.

## O que este template não decide

Não escolhe fornecedor, não fecha contrato e não autoriza o horizonte seguinte. Com este arquivo preenchido, a versão está desenhada o bastante para implementar o horizonte 1 — e só ele.
