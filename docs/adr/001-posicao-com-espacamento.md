# ADR 001: Posição de tarefas com espaçamento

**Status:** aceito

## Contexto

Ao mover uma tarefa, a ordem dentro da coluna precisa ser mantida. Usar posições sequenciais (1, 2, 3...) obriga a reescrever todas as tarefas abaixo a cada movimento.

## Decisão

A coluna `posicao` é numérica e as tarefas recebem valores espaçados (1000, 2000, 3000...). Ao inserir entre duas tarefas, a nova posição é a média das vizinhas. Quando o intervalo fica menor que um limite, a coluna é reindexada.

## Consequências

- Mover uma tarefa normalmente atualiza uma única linha.
- A reindexação é rara e fica isolada no `PosicaoService`, que é testável sem banco.
