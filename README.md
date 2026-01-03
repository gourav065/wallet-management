# Wallet Management System (Spring Boot)

This project is a backend **Wallet Management application** developed using **Spring Boot**.  
The main purpose of this project is to practice and implement **secure REST APIs**, **JWT-based authentication**, and **wallet transaction handling** in a real-world style backend setup.

The application allows users to register, log in, manage wallet balance, and view transaction history.

---

## 📋 What this project does

- User registration and login
- JWT-based authentication and authorization
- Wallet balance creation and management
- Credit and debit wallet transactions
- Transaction history tracking
- Secure logout using token invalidation
- Clean layered architecture (Controller, Service, Repository)
- Unit and integration testing support
- Docker support for easy local setup

---

## 🛠️ Tech stack used

- Java 17
- Spring Boot
- Spring Security (JWT)
- Spring Data JPA
- Hibernate
- Maven
- MySQL / H2 (configurable)
- Docker & Docker Compose
- JUnit and Mockito
- Swagger (OpenAPI)

---

## 📂 Project structure (simplified)
```
src/main/java/com/wallet/
├── controller/      → REST APIs
├── service/         → Business logic
├── repository/      → Database operations
├── model/           → Entities
├── dto/             → Request and response objects
└── config/          → Security, JWT and Swagger configuration
```

---

## 🔐 Authentication flow

1. User logs in using credentials
2. Backend generates a JWT token
3. Token is sent in request headers for secured APIs
4. Logout invalidates the token so it cannot be reused

**Header format:**
```
Authorization: Bearer <JWT_TOKEN>
```

---

## 🌐 API overview

### Authentication APIs
- `POST /auth/register` – Register a new user
- `POST /auth/login` – Login and receive JWT token
- `POST /auth/logout` – Logout user

### Wallet APIs
- `GET /wallet` – Get wallet details
- `POST /wallet/credit` – Add amount to wallet
- `POST /wallet/debit` – Deduct amount from wallet

### Transaction APIs
- `GET /transactions` – View transaction history

---

## 🚀 How to run the project locally

### Prerequisites
- Java 17 or above
- Maven
- Git
- MySQL (optional, H2 can also be used)
- Docker (optional)

---

### 1. Clone the repository
```bash
git clone https://github.com/gourav065/wallet-management.git
cd wallet-management
```

---

### 2. Configure application properties

Create your own configuration file (this file is ignored by Git):

**Path:** `src/main/resources/application.yml`

**Example:**
```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/wallet_db
    username: root
    password: password

jwt:
  secret: my-secret-key
  expiration: 3600000
```

---

### 3. Run using Maven
```bash
mvn clean install
mvn spring-boot:run
```

---

### 4. Run using Docker (optional)
```bash
docker-compose up --build
```

---

## 🧪 Running tests
```bash
mvn test
```

---

## 📖 Swagger API documentation

After starting the application, open:
```
http://localhost:8080/swagger-ui/index.html
```

---

## 📝 Notes

- Sensitive files like `application.yml` are excluded using `.gitignore`
- Passwords are encrypted using **BCrypt**
- JWT validation is handled using a custom security filter

---

## 🚧 Future improvements

- Role-based access control (Admin/User)
- Wallet-to-wallet transfer
- Pagination for transactions
- Redis for token management
- CI/CD pipeline

---

## 👤 Author

**Gourav Verma**  
Java Backend Developer  
(Spring Boot | REST APIs | Security)

---

## 📬 Contact

- **GitHub:** [@gourav065](https://github.com/gourav065)
- **LinkedIn:** [Gourav Verma](https://www.linkedin.com/in/gouravjverma/)
- **Email:** gouravv065@gmail.com

---

## ⚠️ Disclaimer

This project is created for **learning and practice purposes** and follows common backend development best practices.
