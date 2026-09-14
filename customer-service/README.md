# customer-service

DCEP microservice — Customer Profile, Account Management, Preferences, Notifications

## Run

```bash
mvn spring-boot:run
```

Service starts on port **9413**.

## Base URL

```
http://46.250.226.123:9413/api/v1/customers
```

## Endpoints (POC — in-memory store)

| Method | Path                        | Description          |
|--------|-----------------------------|-----------------------|
| GET    | /api/v1/customers/health      | Health check          |
| GET    | /api/v1/customers             | List all Customer     |
| GET    | /api/v1/customers/{id}        | Get one by id         |
| POST   | /api/v1/customers             | Create                |
| PUT    | /api/v1/customers/{id}        | Update                |
| DELETE | /api/v1/customers/{id}        | Delete                |

Actuator health also available at `/actuator/health`.

> This is an MVP/POC scaffold: in-memory storage, no auth, no persistence.
> Next steps: swap `ConcurrentHashMap` store for Spring Data JPA + a real
> datasource (Azure SQL / Cosmos DB per the architecture diagram), add
> DTOs/mapping instead of exposing the entity directly, and wire in
> Spring Security once the Identity Provider is chosen.
