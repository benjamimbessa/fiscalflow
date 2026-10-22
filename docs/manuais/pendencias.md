# Pendências: FiscalFlow

Registro do que ficou por fazer, por conferir ou por decidir no projeto `fiscalflow`. Cada projeto tem o seu próprio arquivo de pendências, com numeração própria.

## Como usar

- **Toda tarefa neste projeto termina conferindo este registro.** O que não foi resolvido nela entra aqui, no mesmo commit da entrega. Isso vale para o que ficou sem testar ou sem validar, as decisões que dependem do Benjamim, os defeitos achados fora do escopo, o ambiente que precisa de ajuste e os passos que só o Benjamim pode dar.
- **Uma pendência por linha**, na tabela, com:
  - `Id` sequencial do projeto (`P-0001`, `P-0002`…; o próximo é o maior + 1, contando as Resolvidas);
  - a data em que foi aberta;
  - o projeto (`fiscalflow`; outro nome só quando a pendência alcança mais de um projeto);
  - o que falta e por quê, em uma ou duas frases;
  - quem resolve (**Benjamim** quando é decisão ou acesso dele, **Claude** quando é trabalho que uma sessão pode fazer);
  - a origem (tarefa, branch, commit ou documento).
- **Ordem crescente de `Id` em todas as tabelas**, inclusive em Resolvidas. Quem abre ou move uma linha a põe no lugar dela, nunca no fim.
- **Resolveu, move** a linha para [Resolvidas](#resolvidas), com a data e o commit (ou o branch) da solução. Pendência não é apagada: se deixou de fazer sentido, vai para Resolvidas com o motivo.
- **Número repetido no merge.** Branches que abrem pendências ao mesmo tempo podem pegar o mesmo `Id`. No merge, fica com o número quem chegou primeiro ao branch principal; a outra ganha o próximo livre, a origem anota o número antigo ("aberta como P-NNNN") e as referências a ela neste arquivo são acertadas.
- **Pendência que alcança outro projeto** é aberta no projeto onde o trabalho será feito, e a origem cita o outro. Uma sessão registra só no arquivo do projeto em que trabalha; o que descobre sobre outro projeto vai para o relatório final, na seção **Pendências**, com a linha pronta para o arquivo de lá.
- Este arquivo é a fonte; o `.html` irmão é gerado.

## Abertas

| Id | Aberta | Projeto | Pendência | Quem | Origem |
|---|---|---|---|---|---|
| P-0001 | 22/10/2026 | fiscalflow | **Versão do .NET divergente.** Todos os `.csproj` estão em `net10.0`, mas o CI (`.github/workflows/ci.yml`) instala só o SDK `8.0.x`, o que deve fazer o build do GitHub falhar com `NETSDK1045`; o diagrama do `README.md` e o `ROADMAP.md` ainda dizem .NET 8. Decidir a versão-alvo e alinhar CI, README e ROADMAP | Benjamim | branch `docs/definicoes-manuais` (seção Run locally do README) |
| P-0002 | 22/10/2026 | fiscalflow | **Conferir os comandos de verificação da infraestrutura** do README (`pg_isready`, `docker compose ps dynamodb`, `/_localstack/health`) com `docker compose up -d` rodando. Só `dotnet test` foi executado (1 teste, `Passed!`); os containers não foram subidos | Claude | branch `docs/definicoes-manuais` |

## Resolvidas

| Id | Aberta | Projeto | Pendência | Resolvida | Solução |
|---|---|---|---|---|---|
