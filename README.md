# Global Solution — NASA Asteroid Monitoring API

## Sobre o Projeto

Este projeto foi desenvolvido para a Global Solution FIAP com o objetivo de monitorar e armazenar informações sobre asteroides utilizando dados da API oficial da NASA (NeoWs — Near Earth Object Web Service).

A aplicação foi desenvolvida utilizando Java Spring Boot, Oracle Database, Docker e Swagger/OpenAPI.

---

# Tecnologias Utilizadas

* Java 21
* Spring Boot
* Spring Security
* JWT Authentication
* Spring Data JPA
* Hibernate
* Oracle Database
* Swagger OpenAPI
* Docker
* Maven

---

# Objetivo da Solução

A solução permite:

* Consumir dados da API da NASA
* Armazenar informações de asteroides
* Gerenciar avaliações de risco
* Disponibilizar endpoints REST
* Documentar automaticamente a API com Swagger
* Utilizar autenticação JWT

---

# Arquitetura do Projeto

O projeto foi organizado em camadas:

```text id="z6fln7"
src/main/java
│
├── controller
├── service
├── repository
├── model
├── dto
├── config
├── security
└── exception
```

---

# Docker

A aplicação foi preparada para execução utilizando Docker.

## Executar containers

```bash id="2woow5"
docker-compose up --build
```

---

# Configuração da Aplicação

Arquivo:

```text id="v00ehm"
application.properties
```

Exemplo:

```properties id="5lq8qb"
spring.application.name=global-solution

spring.datasource.url=jdbc:oracle:thin:@oracle.fiap.com.br:1521:ORCL
spring.datasource.username=SEU_USUARIO
spring.datasource.password=SUA_SENHA

nasa.api.key=SUA_API_KEY

jwt.secret=senhaSecreta
jwt.expiration=30
```

---

# Swagger

Após iniciar a aplicação:

```text id="gbkmm7"
http://localhost:8080/swagger-ui/index.html
```

---

# Autenticação JWT

A aplicação utiliza autenticação JWT com Spring Security.

Endpoint:

```text id="z0p3tr"
POST /auth/login
```

---

# Endpoints Principais

## NASA

| Método | Endpoint         |
| ------ | ---------------- |
| POST   | /nasa/sync/today |
| POST   | /nasa/sync       |

---

## Risk Assessments

| Método | Endpoint               |
| ------ | ---------------------- |
| GET    | /risk-assessments      |
| GET    | /risk-assessments/{id} |
| POST   | /risk-assessments      |
| PUT    | /risk-assessments/{id} |
| DELETE | /risk-assessments/{id} |

---

# Banco de Dados

O projeto utiliza Oracle Database com persistência através do Spring Data JPA e Hibernate.

Principais entidades:

* Asteroid
* RiskAssessment
* User

---

# Vídeo da Apresentação

Link do vídeo:

```text id="w0s7j7"
https://www.youtube.com/watch?v=Pi8j2iX6FMc
```

---

# Integrantes

| Nome | RM |
|------|-----|
|Nathan Gonçalves Pereira Mendes | RM564666 |
|Guilherme Santos Fonseca | RM564232 |
|Gustavo Araujo Da Silva | RM566526 |
|Anthony De Souza Henriques | RM566188 |

---

# Repositório GitHub

```text id="76th1w"
https://github.com/GlobalSolution-Fiap-2TDSPX-2026/DevOpsNei
```

---

# Funcionalidades Implementadas

* API REST com Spring Boot
* Integração com API NASA
* Persistência Oracle
* CRUD completo
* Swagger/OpenAPI
* Docker
* JWT Authentication
* Estrutura em camadas
* Tratamento global de exceções

---

# Considerações Finais

Este projeto foi desenvolvido com foco em arquitetura REST, integração com APIs externas, persistência de dados e boas práticas utilizando o ecossistema Spring.
