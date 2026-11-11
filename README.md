# Countries Server API (ASP.NET Core)

A REST API for a countries-exploration app: country data, personal country lists, quizzes, user shares, an admin panel and an AI assistant. Server-side development course project at Ruppin Academic Center.

## Tech stack
- ASP.NET Core Web API (C#, .NET 6)
- SQL Server with stored procedures (DAL layer)
- OpenAI API for the AI assistant
- Swagger for API docs

## Endpoints
| Controller | Main routes |
|-----------|-------------|
| Users | `POST Register`, `POST Login`, `POST Logout`, `GET {id}` |
| Countries | `GET`, `GET {id}`, `GET FilterOptions`, `POST Import`, `POST`, `PUT`, `DELETE` |
| Lists | `POST`, `GET {userId}/{listType}`, `PUT`, `DELETE` |
| Quiz | `GET`, `GET {quizId}/Questions`, `POST {quizId}/Start`, `POST Submit`, attempts and points |
| Shares | `GET`, `GET ByCountry/{id}`, `POST`, `PUT`, `DELETE` |
| Admin | users, lock/share permissions, delete shares, statistics |
| AI | `POST Ask` |

## Setup
1. Clone the repo and open `CountriesServers.slnx` in Visual Studio.
2. Create `CountriesServers/appsettings.Local.json` (it is git-ignored) with your real values:
```json
{
  "ConnectionStrings": { "myProjDB": "Data Source=...;Initial Catalog=...;User ID=...;Password=..." },
  "OpenAI": { "ApiKey": "sk-..." }
}
```
   You can also set the `OPENAI_API_KEY` environment variable.
3. Run the project and open `/swagger`.

## Structure
- `Controllers/` – API endpoints
- `Models/` – business logic and DTOs
- `DAL/` – database access (`DBservices`)
- `Services/` – OpenAI and external countries API

## Authors
Adam Elmalek
