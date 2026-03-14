# PostgreSQL (Docker)

Stack PostgreSQL pronto para uso em desenvolvimento local.

## Arquivos

- docker-compose.yml: definicao do servico PostgreSQL
- postgres-init/: scripts opcionais de inicializacao (executados somente na primeira subida com banco vazio)

## Credenciais padrao (dev local)

- usuario: postgres
- senha: postgres
- banco: app_db
- porta: 5432

## Como subir

1. Entre na pasta postgres:

    cd postgres

2. Suba o container em background:

    docker compose up -d

3. Verifique o status:

    docker compose ps

4. Teste a conexao com SQL:

    docker compose exec -T postgres psql -U postgres -d app_db -c "SELECT current_database(), current_user, version();"

## Como parar

    docker compose down

## Como remover tambem os dados (volume)

    docker compose down -v

## Observacoes

- O volume nomeado postgres_data persiste os dados entre reinicios/recriacao do container.
- A pasta postgres-init pode conter arquivos .sql e .sh para bootstrap do banco.
