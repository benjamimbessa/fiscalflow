## Imported Claude Cowork project instructions

### Documentação: sempre .md + .html

Decisão do Benjamim (2026-10-11), vale para todos os projetos em `P:\` e para Claude Code, Claude Cowork e Claude Desktop:

- Toda documentação criada ou alterada em `.md` (README, `docs/`, levantamentos, propostas, ADRs, roadmaps, relatórios, guias) ganha um `.html` irmão, com o mesmo nome e na mesma pasta. O `.md` **continua sendo criado** e é a fonte; o `.html` é a versão para leitura no navegador.
- Gere o HTML com `python P:\files\tools\md2html\md2html.py <arquivo.md>` (ou `--scan <pasta>`). No Claude Code isso já acontece sozinho por hook a cada Write/Edit; confira que o `.html` saiu. No Cowork e no Desktop, rode o comando depois de salvar o `.md`. Sem acesso ao script, gere à mão um HTML autocontido (CSS embutido, tema claro/escuro, sumário das seções, tabelas legíveis, links `.md` trocados por `.html`) com o mesmo conteúdo.
- Não edite o `.html` à mão: altere o `.md` e regere. Renomeou ou apagou o `.md`, faça o mesmo com o `.html`. Os dois entram no mesmo commit.
- Não se aplica a arquivos de instrução de agente (`CLAUDE.md`, `AGENTS.md`, `SKILL.md`, memória, skills).
- Detalhes: `P:\files\tools\md2html\README.md`.
