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

Local: postgres/docker-compose.yml

Principais pontos:

- imagem oficial postgres:17-alpine
- volume nomeado para persistencia de dados
- healthcheck com pg_isready
- reinicio automatico com unless-stopped
- scripts de inicializacao opcionais em postgres/postgres-init

Credenciais atuais para dev local:

- usuario: postgres
- senha: postgres
- banco: app_db
- porta: 5432

## Como subir o PostgreSQL

1. Entre na pasta do app:

    cd postgres

2. Suba em background:

    docker compose up -d

3. Verifique status:

    docker compose ps

4. Teste conexao com consulta SQL:

    docker compose exec -T postgres psql -U postgres -d app_db -c "SELECT current_database(), current_user, version();"

## Como parar e remover o stack

Dentro da pasta postgres:

    docker compose down

Para remover tambem os dados persistidos:

    docker compose down -v

## Convencoes do repositorio

- uma pasta por app Docker
- cada app com seu proprio docker-compose.yml
- comentarios explicando decisoes importantes no compose
- commits seguindo Conventional Commits

## Status

- PostgreSQL: pronto para uso e testado
- Redis: planejamento iniciado
