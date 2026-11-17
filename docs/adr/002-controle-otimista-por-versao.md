# ADR 002: Controle de concorrência otimista por versão

**Status:** aceito

## Contexto

Duas abas (ou dois dispositivos) podem editar ou mover a mesma tarefa ao mesmo tempo, e a última escrita sobrescreveria a anterior sem aviso.

## Decisão

A tabela `tarefa` tem a coluna `versao`. Toda atualização usa `WHERE id = ? AND versao = ?` e incrementa a versão. Se nenhuma linha for afetada, a API responde `409 Conflict`.

## Consequências

- Conflitos são detectados sem bloqueios longos.
- O front precisa tratar o 409, desfazer a atualização otimista e recarregar a tarefa.
