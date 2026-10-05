# 3DPrintHub

Loja online de impressão 3D: o cliente compra modelos do catálogo ou envia o seu próprio ficheiro (.stl, .3mf, .obj); nós orçamentamos, imprimimos e enviamos.

## Estrutura do repositório
| Pasta | Conteúdo | Equipa |
|---|---|---|
| `backend/` | API REST em Java 21, Spring Boot 3, MySQL (Aiven) e Flyway | Grupo 2 |
| `frontend/` | Site em React + Vite | Grupo 1 |
| `docs/` | Atas, diagramas e relatório | Ambas |

Cada pasta tem o seu README com as instruções para arrancar.

## Regras comuns
- Nunca trabalhar diretamente na `main`: uma branch por tarefa (`feature/login-jwt`, `fix/upload-tamanho`).
- Commits: `feat:`, `fix:`, `docs:` + frase curta no presente.
- Pull request com 1 aprovação de outra pessoa, ligado à tarefa do quadro e com "como testar".
- Nunca fazer commit de passwords ou chaves (`.env` está no `.gitignore`).
- Qualquer mudança a um endpoint é avisada à outra equipa antes de entrar na `main`.
