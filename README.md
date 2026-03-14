# Docker Apps

Repositorio agregador de apps Docker prontos para uso, com configuracoes testadas e foco em desenvolvimento local rapido.

## Objetivo

Este projeto centraliza stacks Docker reutilizaveis (banco, cache, fila, observabilidade, etc.) em pastas separadas por app.
A proposta e:

- subir servicos em poucos comandos
- manter boas praticas de compose
- ter exemplos com comentarios para facilitar aprendizado e manutencao
- validar os stacks antes de considerar como pronto para uso

## Estrutura

- postgres/: stack do PostgreSQL
- redis/: stack do Redis (em construcao)

## Stack disponivel

### PostgreSQL

Para ver como subir, testar, parar e configurar o container PostgreSQL, acesse [postgres/README.md](./postgres/README.md).
Arquivo compose do servico: [postgres/docker-compose.yml](./postgres/docker-compose.yml).

## Convencoes do repositorio

- uma pasta por app Docker
- cada app com seu proprio docker-compose.yml
- comentarios explicando decisoes importantes no compose
- commits seguindo Conventional Commits

## Status

- PostgreSQL: pronto para uso e testado
- Redis: planejamento iniciado
