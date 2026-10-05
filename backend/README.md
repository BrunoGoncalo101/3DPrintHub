# 3DPrintHub: Back-end

API REST (Java 21, Spring Boot 3, MySQL na Aiven, Flyway).

## Como arrancar
1. Entrar na pasta: `cd backend`
2. Copiar `.env.example` para `.env` e preencher `DB_URL`, `DB_USER`, `DB_PASSWORD` e `JWT_SECRET` (as credenciais da base de dados pedem-se ao B, em privado).
3. Correr: `mvn spring-boot:run`
4. A API fica em `http://localhost:8080`.

> O `.env` tem de estar dentro de `backend/` (é onde se corre o comando). Nunca fazer commit dele.

## Base de dados
- Só se altera por migrações Flyway em `src/main/resources/db/migration` (`V1__...`, `V2__...`).
- Uma migração já aplicada nunca se edita: cria-se uma nova.
- O Hibernate está em `ddl-auto=validate`: não altera tabelas.
- Os ficheiros 3D ficam na pasta `uploads/`, não na base de dados.

## Estrutura (`pt.loja3d`)
`controller` → `service` → `repository`, mais `model`, `dto`, `config` e `exception`.

## Convenções
- Erros da API num único formato JSON: `{"erro": "mensagem", "codigo": 400}`.
- Endpoints no plural, em português, sem verbos no caminho.
- A API nunca devolve entidades diretamente: usar DTOs.

## Equipa
| Pessoa | Módulo | Nome |
|---|---|---|
| A | Utilizadores e segurança + DevOps | |
| B | Catálogo + DBA | |
| C | Ficheiros 3D e orçamentos + QA | |
| D | Encomendas e pagamentos + Docs API | |
