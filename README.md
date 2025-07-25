

# 🔐 Login Auth API

Uma API REST desenvolvida com Spring Boot para autenticação e registro de usuários utilizando **JWT (JSON Web Token)** e **Spring Security**.

---

## 📦 Funcionalidades

- Cadastro de usuário (`/auth/register`)
- Login e geração de token JWT (`/auth/login`)
- Acesso a endpoint protegido com autenticação (`/user`)
- Validação de token em requisições protegidas
- Configuração de CORS para integração com frontend Angular

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia        | Ícone |
|-------------------|-------|
| Java              | ![Java](https://img.shields.io/badge/-Java-000?logo=java&logoColor=white&style=flat-square) |
| Spring Boot       | ![Spring Boot](https://img.shields.io/badge/-Spring_Boot-000?logo=spring-boot&logoColor=6DB33F&style=flat-square) |
| Spring Security   | ![Spring Security](https://img.shields.io/badge/-Spring_Security-000?logo=spring&logoColor=6DB33F&style=flat-square) |
| JWT               | ![JWT](https://img.shields.io/badge/-JWT-000?logo=json-web-tokens&logoColor=white&style=flat-square) |
| PostgreSQL        | ![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-000?logo=postgresql&logoColor=white&style=flat-square) |
| Maven             | ![Maven](https://img.shields.io/badge/-Maven-000?logo=apache-maven&logoColor=white&style=flat-square) |
| Lombok            | ![Lombok](https://img.shields.io/badge/-Lombok-000?logo=java&logoColor=white&style=flat-square) |
| H2 Database       | ![H2](https://img.shields.io/badge/-H2_DB-000?logo=h2&logoColor=white&style=flat-square) |

---

## 📁 Estrutura de Pastas

src/
└── main/
├── java/
│ └── com.example.login_auth_api/
│ ├── controller/
│ ├── domain/
│ ├── dto/
│ ├── infra/
│ │ └── security/
│ └── repository/
└── resources/
└── application.properties


---

## ⚙️ Como Executar Localmente

### Pré-requisitos

- Java 21
- Maven
- PostgreSQL rodando localmente

---

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/login-auth-api.git
cd login-auth-api

2. Configure o application.properties

Edite o arquivo src/main/resources/application.properties com os dados do seu banco:

spring.datasource.url=jdbc:postgresql://localhost:5432/login_auth_api
spring.datasource.username=postgres
spring.datasource.password=28082023
api.security.token.secret=28082023

3. Rode o projeto

./mvnw spring-boot:run

🔐 Endpoints
1. Registrar

POST /auth/register

{
  "name": "Fulano da Silva",
  "email": "fulano@email.com",
  "password": "123456"
}

2. Login

POST /auth/login

{
  "email": "fulano@email.com",
  "password": "123456"
}

Resposta:

{
  "name": "Fulano da Silva",
  "token": "Bearer eyJhbGciOiJIUzI1NiIs..."
}

3. Endpoint protegido

GET /user
Requer header de autorização:

Authorization: Bearer <token>

Resposta:

"sucesso"

🧠 Conceitos Importantes

    Stateless Authentication: o sistema não guarda sessões no servidor, apenas tokens JWT.

    Spring Security FilterChain: configuração de rotas públicas e protegidas.

    CORS habilitado para permitir requisições do frontend Angular (localhost:4200).

🧪 Testes

A API pode ser testada com ferramentas como:

    Postman

    Insomnia

👨‍💻 Autor

Desenvolvido com 💙 por Jonata Freitas
🔗 @JonataDev
