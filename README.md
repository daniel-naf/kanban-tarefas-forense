# kanban-tarefas-forense
Kanban pessoal de tarefas com visual inspirado em laboratório forense, em Spring Boot, PostgreSQL e React. Inclui histórico de atividades e exportação em CSV.

## Stack

- **Back-end:** Java 21, Spring Boot, Spring Security (JWT), Spring Data JPA, Flyway
- **Banco:** PostgreSQL
- **Front-end:** React, Vite, TypeScript, dnd-kit, TanStack Query
- **Testes:** JUnit 5, MockMvc, Testcontainers

## Estrutura

```
backend/    API Spring Boot
frontend/   Aplicação React
docs/       Arquitetura e registros de decisão (ADRs)
```

## Documentação

- [Arquitetura](docs/arquitetura.md)
- [Decisões técnicas (ADRs)](docs/adr/)

## Rodando localmente

```bash
docker compose up -d   # sobe o PostgreSQL
```

> Projeto em desenvolvimento.
