# 🚚 Fast Moving API

![Java](https://img.shields.io/badge/Java-22-orange?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.0-brightgreen?style=for-the-badge&logo=springboot&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-2022-red?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-UI-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)
![Status](https://img.shields.io/badge/Status-Em%20desenvolvimento-yellow?style=for-the-badge)

## 📋 Sobre o projeto

API REST desenvolvida como Trabalho de Conclusão de Curso (TCC) na **Etec Horácio Augusto da Silveira**, evoluída para portfólio profissional.

O sistema **Fast Moving** é uma plataforma de contratação de serviços de mudança e locação, conectando clientes a prestadores de serviço. A API gerencia todo o fluxo de contratos, prestadores, veículos e pagamentos.

---

## 🚀 Tecnologias utilizadas

- **Java 22**
- **Spring Boot 3.4.0**
- **Spring Data JPA + Hibernate 6**
- **SQL Server 2022**
- **Lombok**
- **Swagger UI (SpringDoc OpenAPI 2.1)**
- **Maven**

---

## 📁 Estrutura do projeto

```
src/main/java/com/FastMoving/api_locadora/
├── controller/         → Endpoints REST (um por entidade)
├── dao/                → Interfaces JPA (repositórios)
├── domain/
│   ├── model/          → Entidades mapeadas do banco
│   └── ports/          → Interfaces de entrada e saída
├── infraestructure/
│   └── adapters/       → Implementações externas
├── usecase/
│   └── implementation/ → Regras de negócio
├── DTO/                → Objetos de transferência de dados
└── Enum/               → Enumerações (ex: StatusVeiculo)
```

---

## 🗄️ Modelo de dados

O banco de dados `FAST_201902` no SQL Server contém as seguintes tabelas:

| Tabela | Descrição |
|---|---|
| `cliente` | Dados dos clientes |
| `prestador` | Prestadores de serviço |
| `pessoa` | Funcionários vinculados a empresas |
| `empresa` | Empresas cadastradas |
| `veiculo` | Veículos dos prestadores |
| `contrato_servico` | Contratos entre cliente e prestador |
| `tp_serv` | Tipos de serviço (mudança, locação) |
| `tp_pgto` | Tipos de pagamento |
| `tp_pessoa` | Tipos de pessoa (física, jurídica) |
| `cartao` | Dados de cartão de pagamento |

---

## ⚙️ Como executar

### Pré-requisitos

- Java 22+
- Maven
- SQL Server 2022

### Configuração do banco

1. Crie o banco `FAST_201902` no SQL Server
2. Execute o script `SCRIPT_TCC_CORRIGIDO.sql` disponível na raiz do projeto
3. Crie um login SQL Server:

```sql
CREATE LOGIN fastmoving WITH PASSWORD = 'sua_senha';
CREATE USER fastmoving FOR LOGIN fastmoving;
ALTER ROLE db_owner ADD MEMBER fastmoving;
```

### Configuração da aplicação

Edite o arquivo `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:sqlserver://SEU_SERVIDOR:1433;databaseName=FAST_201902;encrypt=true;trustServerCertificate=true
spring.datasource.username=fastmoving
spring.datasource.password=sua_senha
```

### Executando

```bash
mvn spring-boot:run
```

A API estará disponível em `http://localhost:8080`

---

## 📖 Documentação

A documentação interativa da API está disponível via Swagger UI:

```
http://localhost:8080/swagger-ui/index.html
```

---

## 📌 Endpoints disponíveis

| Método | Endpoint | Descrição |
|---|---|---|
| GET | `/cartao` | Lista todos os cartões |
| GET | `/cartao/{id}` | Busca cartão por ID |
| POST | `/cartao` | Cadastra novo cartão |
| PUT | `/cartao/{id}` | Atualiza cartão |
| DELETE | `/cartao/{id}` | Remove cartão |
| GET | `/cliente` | Lista todos os clientes |
| GET | `/cliente/{id}` | Busca cliente por ID |
| POST | `/cliente` | Cadastra novo cliente |
| PUT | `/cliente/{id}` | Atualiza cliente |
| DELETE | `/cliente/{id}` | Remove cliente |
| GET | `/veiculo` | Lista todos os veículos |
| GET | `/prestador` | Lista todos os prestadores |
| GET | `/contrato` | Lista todos os contratos |

> Consulte o Swagger UI para a lista completa e exemplos de requisição.

---

## 👨‍💻 Autor

**Gustavo Xavier**  
[![GitHub](https://img.shields.io/badge/GitHub-GustavoXavier--hub-181717?style=flat&logo=github)](https://github.com/GustavoXavier-hub)
