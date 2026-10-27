## Overview

Order & Inventory API is a RESTful backend service for managing a product catalog, maintaining inventory levels, and processing customer orders.

The application focuses on realistic business rules:

- Inventory levels must never become negative.
- An order can be created only when sufficient stock is available.
- Order creation and inventory updates must remain consistent.
- Concurrent requests must not cause overselling.
- Retrying a request should not accidentally create duplicate orders once idempotency is implemented.


## Goals

- Build a REST API using ASP.NET Core.
- Design a relational data model using Entity Framework Core.
- Work with PostgreSQL, database constraints, indexes, and migrations.
- Implement transactions and handle concurrent inventory updates.
- Write unit and integration tests.
- Containerize the application with Docker.
- Automate builds and tests using CI/CD.
- Document architectural decisions and API contracts.


## Tech Stack

| Technology | Purpose |
|---|---|
| C# | Main programming language |
| .NET 10 | Application platform |
| ASP.NET Core | REST API and HTTP pipeline |
| Entity Framework Core 10 | ORM and database access |
| PostgreSQL | Relational database |
| Docker Compose | Local development environment |
| xUnit | Automated testing |
| OpenAPI / Swagger | API documentation |
| GitHub Actions | CI/CD automation (planned) |


## Architecture

The solution is split into projects to separate business logic from infrastructure concerns.

```text
src/
├── Orders.Api/
│   ├── Controllers/
│   ├── Middleware/
│   └── Program.cs
├── Orders.Application/
│   ├── Orders/
│   ├── Products/
│   └── Abstractions/
├── Orders.Domain/
│   ├── Entities/
│   ├── Enums/
│   └── Exceptions/
└── Orders.Infrastructure/
    ├── Persistence/
    ├── Repositories/
    └── Configurations/

tests/
├── Orders.UnitTests/
└── Orders.IntegrationTests/
```


## Roadmap

- [ ] Implement the initial domain model.
- [ ] Configure PostgreSQL and EF Core migrations.
- [ ] Implement product management endpoints.
- [ ] Implement order creation and cancellation.
- [ ] Add transactional inventory reservation.
- [ ] Add concurrency integration tests.
- [ ] Add idempotency support.
- [ ] Add centralized exception handling and validation.
- [ ] Add pagination and filtering.
- [ ] Containerize the application.
- [ ] Set up CI with automated tests.
- [ ] Add authentication and authorization.
- [ ] Add structured logging, health checks, and OpenTelemetry.
- [ ] Introduce an outbox and background processing.
- [ ] Deploy the application to Azure.