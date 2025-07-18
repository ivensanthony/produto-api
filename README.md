# produto-api
# Produto API - Spring Boot + PostgreSQL + Docker

Este projeto é uma API RESTful desenvolvida com *Spring Boot, que permite o cadastro, consulta, atualização e exclusão de produtos. A aplicação está integrada ao **PostgreSQL via Docker, utilizando **JPA* para persistência.

---

## ✅ Tecnologias Utilizadas

- Java 21
- Spring Boot 3.5.3
- Spring Data JPA
- PostgreSQL (Docker)
- Maven
- Lombok
- Thunder Client (para testes)

---

## 📦 Entidade Produto

| Campo      | Tipo     |
|------------|----------|
| id         | Long     |
| nome       | String   |
| descricao  | String   |
| preco      | Double   |
| quantidade | Integer  |

---

## 🚀 Como Executar

### 1️⃣ Suba o banco de dados com Docker:

```bash
docker run --name nap01dev \
  -e POSTGRES_DB=produto_db \
  -e POSTGRES_USER=aula \
  -e POSTGRES_PASSWORD=senha \
  -p 5428:5432 \
  -d postgres

---

## Configure o arquivo application.properties:
spring.application.name=Produto-api
spring.datasource.url=jdbc:postgresql://localhost:5428/produto_db
spring.datasource.username=aula
spring.datasource.password=senha

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect

---

## Rode a aplicação:
Via terminal:

```bash

./mvnw spring-boot:run

---

Via Spring Tool Suite:
- produto-api (pasta do projeto)
- Run As
- Spring boot app

---

## Testes com Thunder Client
Use o Thunder Client (VS Code) para testar os endpoints.
endereço: "http://localhost:8080/produtos"

---

## Endpoints da API
Descrição:
GET	/produtos	- Lista todos os produtos
GET	/produtos/{id} - Retorna um produto por ID
POST	/produtos	- Cadastra um novo produto
PUT	/produtos/{id}	- Atualiza um produto existente
DELETE	/produtos/{id}	- Remove um produto por ID

---

## Exemplo de JSON para POST/PUT
Body/json
Copiar código
{
  "nome": "Monitor",
  "descricao": "Monitor LED 24 polegadas",
  "preco": 899.90,
  "quantidade": 10
}



