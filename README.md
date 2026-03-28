# Smart Clinic Management System

A complete microservices capstone-style project with:
- Config Server
- Eureka Service Registry
- API Gateway
- patient-service (MySQL)
- appointment-service (MongoDB)
- billing-service (MySQL)
- React frontend (Vite)
- Docker Compose for databases

## Requirements
- Java 17+
- Maven 3.9+
- Node.js 20+
- Docker Desktop

## Run order
1. `docker compose up -d`
2. `platform/config-server`
3. `platform/service-registry`
4. `service/patient-service`
5. `service/appointment-service`
6. `service/billing-service`
7. `platform/api-gateway`
8. `webapp`

## Start databases
```bash
docker compose up -d
```

## Start backend services
Open a new terminal for each service.

### Config Server
```bash
cd platform/config-server
mvn spring-boot:run
```

### Service Registry
```bash
cd platform/service-registry
mvn spring-boot:run
```

### Patient Service
```bash
cd service/patient-service
mvn spring-boot:run
```

### Appointment Service
```bash
cd service/appointment-service
mvn spring-boot:run
```

### Billing Service
```bash
cd service/billing-service
mvn spring-boot:run
```

### API Gateway
```bash
cd platform/api-gateway
mvn spring-boot:run
```

## Start frontend
```bash
cd webapp
npm install
npm run dev
```

## URLs
- Frontend: http://localhost:5173
- Gateway: http://localhost:8080
- Eureka: http://localhost:8761
- Config Server: http://localhost:8888

## Notes
- The frontend uses a Vite proxy for `/api` to `http://localhost:8080`, so browser CORS issues are avoided.
- The gateway also includes CORS configuration for direct frontend access from `http://localhost:5173`.
- MySQL databases are created automatically from `infra/mysql/init.sql`.
