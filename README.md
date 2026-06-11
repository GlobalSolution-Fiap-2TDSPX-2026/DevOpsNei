# ☄️ Global Solution — NASA Asteroid Monitoring API

## 📌 Sobre o Projeto

Este projeto foi desenvolvido para a Global Solution FIAP com o objetivo de monitorar e armazenar informações sobre asteroides utilizando dados da API oficial da NASA (NeoWs — Near Earth Object Web Service).

A aplicação foi construída utilizando Java Spring Boot, Oracle Database, Docker e Swagger/OpenAPI, aplicando conceitos de desenvolvimento backend, integração com APIs externas, segurança, persistência de dados e DevOps.

---

# 🎯 Objetivo da Solução

O sistema foi criado para consumir dados reais fornecidos pela NASA, armazená-los em banco de dados Oracle e disponibilizá-los através de uma API REST segura e documentada.

Principais objetivos:

* Consumir dados da API NeoWs da NASA;
* Armazenar informações sobre asteroides;
* Gerenciar avaliações de risco;
* Disponibilizar endpoints REST;
* Implementar autenticação JWT;
* Utilizar Docker para padronização do ambiente;
* Documentar a API utilizando Swagger.

---

# 🚀 Tecnologias Utilizadas

### Backend

* Java 21
* Spring Boot
* Spring Security
* Spring Data JPA
* Hibernate
* JWT Authentication

### Banco de Dados

* Oracle Database

### DevOps

* Docker
* Azure Virtual Machine

### Documentação

* Swagger OpenAPI

### APIs Externas

* NASA NeoWs API

---

# ☁️ Infraestrutura e Deploy

A aplicação foi implantada em uma Máquina Virtual (VM) hospedada na Microsoft Azure.

A VM é responsável por:

* Hospedar a aplicação;
* Executar os containers Docker;
* Disponibilizar a API para acesso externo;
* Centralizar o ambiente de execução.

A utilização da nuvem permite que a aplicação fique disponível remotamente para qualquer usuário autorizado.

---

# 🐳 Containerização com Docker

O projeto utiliza Docker para garantir portabilidade e padronização do ambiente.

## Benefícios

* Facilidade de deploy;
* Isolamento dos serviços;
* Reprodutibilidade do ambiente;
* Redução de problemas de configuração.

## Containers Utilizados

| Container       | Função                   |
| --------------- | ------------------------ |
| Spring Boot API | Executa a aplicação Java |
| Banco de Dados  | Persistência dos dados   |

---

# 🏗️ Arquitetura da Solução

A aplicação segue o padrão de Arquitetura em Camadas (Layered Architecture).

Arquitetura_GlobalSolution_Completa.drawio.png

### Controller Layer

Responsável por receber as requisições HTTP e retornar respostas para os clientes.

Exemplos:

* NasaController
* RiskAssessmentController
* AuthController

---

### Service Layer

Contém as regras de negócio da aplicação.

Responsabilidades:

* Consumo da API da NASA;
* Processamento de dados;
* Validações;
* Avaliações de risco.

---

### Repository Layer

Responsável pela comunicação com o banco utilizando Spring Data JPA.

Operações:

* Insert
* Select
* Update
* Delete

---

### Database Layer

Banco Oracle responsável pela persistência das informações.

Principais entidades:

* Asteroid
* RiskAssessment
* User

---

### Security Layer

Implementada com Spring Security e JWT.

Responsabilidades:

* Autenticação;
* Autorização;
* Geração de Tokens;
* Proteção dos endpoints.

---

# 📐 Diagrama de Arquitetura

O projeto possui diagrama de arquitetura desenvolvido no Draw.io representando:

* Cliente/Swagger
* Controllers
* Services
* Repositories
* Oracle Database
* NASA NeoWs API
* Azure VM
* Docker

Arquivo:

```text
docs/Arquitetura_GlobalSolution.drawio
```

---

# 🔄 Fluxo da Aplicação

```text
Usuário
   │
   ▼
Swagger / Cliente REST
   │
   ▼
Controllers
   │
   ▼
Services
   │
   ├── Consulta NASA NeoWs API
   │
   ▼
Repositories
   │
   ▼
Oracle Database
```

---

# 🛰️ Integração com a NASA

A aplicação realiza integração com a API oficial da NASA NeoWs.

Funcionalidades:

* Consulta de asteroides próximos à Terra;
* Consumo de dados astronômicos reais;
* Armazenamento local das informações;
* Geração de avaliações de risco.

---

# 🔒 Segurança

A API utiliza autenticação baseada em JWT (JSON Web Token).

## Recursos Implementados

* Login autenticado;
* Geração de token JWT;
* Proteção de endpoints;
* Controle de acesso.

---

# ⚙️ Configuração da Aplicação

Arquivo:

```properties
application.properties
```

Exemplo:

```properties
spring.application.name=global-solution

spring.datasource.url=jdbc:oracle:thin:@oracle.fiap.com.br:1521:ORCL
spring.datasource.username=SEU_USUARIO
spring.datasource.password=SUA_SENHA

nasa.api.key=SUA_API_KEY

jwt.secret=SEU_SEGREDO
jwt.expiration=30
```

---

# 🐳 Executando com Docker

Subir containers:

```bash
docker-compose up --build
```

Verificar containers:

```bash
docker ps
```

---

# 📡 Documentação Swagger

Após iniciar a aplicação:

```text
http://localhost:8080/swagger-ui/index.html
```

---

# ☄️ Principais Endpoints

## NASA

| Método | Endpoint         |
| ------ | ---------------- |
| POST   | /nasa/sync       |
| POST   | /nasa/sync/today |

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

## Authentication

| Método | Endpoint    |
| ------ | ----------- |
| POST   | /auth/login |

---

# 📁 Estrutura do Projeto

```text
src/main/java
│
├── controller
│
├── service
│
├── repository
│
├── model
│
├── security
│
├── config
│
└── exception
```

---

# 📊 Funcionalidades Implementadas

✅ API REST com Spring Boot

✅ Integração com NASA NeoWs

✅ Oracle Database

✅ Spring Data JPA

✅ Hibernate

✅ Swagger OpenAPI

✅ Docker

✅ JWT Authentication

✅ CRUD Completo

✅ Tratamento Global de Exceções

✅ Arquitetura em Camadas

✅ Deploy em Nuvem

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

# 📂 Repositório GitHub

```text
https://github.com/GlobalSolution-Fiap-2TDSPX-2026/DevOpsNei
```

---

# 📘 Considerações Finais

Este projeto foi desenvolvido com foco na aplicação prática de conceitos de Engenharia de Software, APIs REST, Banco de Dados, Segurança, Cloud Computing e DevOps.

A solução demonstra a integração entre tecnologias modernas do ecossistema Java e serviços externos, utilizando boas práticas de desenvolvimento e arquitetura de software.
