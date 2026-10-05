# Loja de Impressão 3D: Back-end

API REST da loja online de impressão 3D (Java 21, Spring Boot 3, MySQL na Aiven, Flyway).

## Requisitos
- Java 21 (ou 17, conforme as aulas; ajustar `java.version` no `pom.xml`)
- Maven
- Acesso à base de dados Aiven (pedir as credenciais ao B, em privado)

## Como arrancar
1. Clonar o repositório.
2. Copiar `.env.example` para `.env` e preencher `DB_URL`, `DB_USER`, `DB_PASSWORD` e `JWT_SECRET`.
3. Correr:
   ```bash
   mvn spring-boot:run
   ```
4. A API fica em `http://localhost:8080`.

> O `.env` está no `.gitignore`. Nunca fazer commit de passwords ou chaves.

## Base de dados
- Só se altera por migrações Flyway em `src/main/resources/db/migration` (`V1__...`, `V2__...`).
- Uma migração já aplicada nunca se edita: cria-se uma nova.
- O Hibernate está em `ddl-auto=validate`: não altera tabelas.
- Os ficheiros 3D ficam na pasta `uploads/`, não na base de dados.

## Estrutura (`pt.loja3d`)
`controller` → `service` → `repository`, mais `model`, `dto`, `config` e `exception`.

## Regras de trabalho
- Nunca trabalhar diretamente na `main`: uma branch por tarefa (`feature/login-jwt`, `fix/upload-tamanho`).
- Commits: `feat:`, `fix:`, `docs:` + frase curta no presente.
- Pull request com 1 aprovação, ligado à tarefa do quadro e com "como testar".
- Erros da API num único formato JSON: `{"erro": "mensagem", "codigo": 400}`.
- Endpoints no plural, em português, sem verbos no caminho.

## Equipa
| Pessoa | Módulo | Nome |
|---|---|---|
| A | Utilizadores e segurança + DevOps | |
| B | Catálogo + DBA | |
| C | Ficheiros 3D e orçamentos + QA | |
| D | Encomendas e pagamentos + Docs API | |

teste