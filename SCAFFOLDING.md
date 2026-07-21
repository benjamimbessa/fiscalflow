# Day-1 scaffolding (run locally, then delete this file)

```bash
dotnet new sln -n FiscalFlow
dotnet new webapi -n FiscalFlow.Orders.Api -o src/Orders/FiscalFlow.Orders.Api
dotnet new classlib -n FiscalFlow.Orders.Domain -o src/Orders/FiscalFlow.Orders.Domain
dotnet new classlib -n FiscalFlow.Orders.Application -o src/Orders/FiscalFlow.Orders.Application
dotnet new classlib -n FiscalFlow.Orders.Infrastructure -o src/Orders/FiscalFlow.Orders.Infrastructure
dotnet new xunit -n FiscalFlow.Orders.Tests -o tests/FiscalFlow.Orders.Tests
dotnet sln add $(find src tests -name '*.csproj')
# wire references: Api -> Application -> Domain; Infrastructure -> Application
# packages: MediatR, FluentValidation, Npgsql.EntityFrameworkCore.PostgreSQL
```
