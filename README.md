# AI Agent Design Kit

Templates para desenhar uma solução com agente de IA, do processo de negócio até a arquitetura. Preencha na ordem. Cada arquivo usa o artefato anterior como entrada.

O exemplo que atravessa o kit é fictício: o reembolso do Mercado Leme, um marketplace. Leia o exemplo só depois de tentar preencher com o seu processo.

SIPOC, RICE, RACI, JTBD e os 5 Porquês são métodos conhecidos. A adaptação para agentes — rota da tarefa, leitura de viabilidade pela pior dimensão, fila de execução e níveis de autonomia — está organizada aqui como um fluxo único. O texto é para preencher em projeto. Este repositório não implementa agente e não escolhe fornecedor.

## Como usar

1. Copie o arquivo do tema em que você está.
2. Preencha os campos em branco com alguém que executa o processo.
3. Confira o exemplo do Mercado Leme para ver o nível de especificidade esperado.
4. Siga o encadeamento no final do arquivo.

Até o brief, a pergunta é qual problema vale a pena e qual é a rota mais simples que resolve. Modelo e fornecedor entram na arquitetura.

## Ordem

| Ordem | Tema | Templates |
| :--- | :--- | :--- |
| 1 | Descoberta | [SIPOC](discovery/sipoc.md), [radar de oportunidade](discovery/opportunity-radar.md), [mapa de oportunidades](discovery/opportunity-map.md) |
| 2 | Diagnóstico e priorização | [Matriz de diagnóstico de tarefas](diagnosis/task-diagnosis-matrix.md), [Impacto × Viabilidade](diagnosis/impact-viability.md), [AI-RICE](diagnosis/ai-rice.md) |
| 3 | Caso de uso | [Brief](use-case/brief.md), [stakeholders e riscos](use-case/stakeholders-and-risks.md) |
| 4 | Experiência | [Storyboard](experience/storyboard.md), [protótipo conceitual](experience/conceptual-prototype.md) |
| 5 | Evolução | [Roadmap de 3 horizontes](evolution/three-horizons.md) |
| 6 | Arquitetura | [Topologia](architecture/orchestration-topology.md), [memória](architecture/memory.md), [ação e supervisão](architecture/action-and-supervision.md), [escolha do motor](architecture/reasoning-engine.md) |

A arquitetura descreve o horizonte que está em construção. Trocar de horizonte reabre esses quatro arquivos.
