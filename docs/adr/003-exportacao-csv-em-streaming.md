# ADR 003: Exportação CSV em streaming

**Status:** aceito

## Contexto

A exportação de um quadro com muitas tarefas não deve carregar tudo na memória antes de responder.

## Decisão

O endpoint `/api/quadros/{id}/exportar.csv` usa `StreamingResponseBody`, escrevendo linha a linha. O conteúdo segue a RFC 4180 (escape de aspas, vírgulas e quebras de linha) e começa com BOM UTF-8 para o Excel exibir acentos corretamente.

## Consequências

- Uso de memória constante, independente do tamanho do quadro.
- A lógica de escape fica no `CsvWriter`, com testes unitários próprios.
