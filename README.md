
# Microservices Dockerized Project

This repository contains four Node.js microservices:

- **User Service** (Port 3000)  
- **Product Service** (Port 3001)  
- **Order Service** (Port 3002)  
- **Gateway Service** (Port 3003)

Each service is containerized using Docker and orchestrated with Docker Compose to enable easy setup and inter-service communication.

## Project Structure

```
Microservices/
├── user-service/
│   └── Dockerfile
├── product-service/
│   └── Dockerfile
├── order-service/
│   └── Dockerfile
├── gateway-service/
│   └── Dockerfile
├── docker-compose.yml
└── README.md
```

## Prerequisites

- Docker installed on your system  
- Docker Compose installed  
- Git installed 

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/minnathdhani/Microservices-Task.git
cd Microservices-Task/Microservices
```

### 2. Build and Start All Services

```bash
docker-compose up 
```

### Screenshot: Docker Compose Output

-![Screenshot 2025-05-10 185759](https://github.com/user-attachments/assets/4bdd5de9-142b-4ccc-ad9e-61201283f463)

-![Screenshot 2025-05-10 185817](https://github.com/user-attachments/assets/33ead333-a715-42ab-abbf-6a567022639e)

-![Screenshot 2025-05-10 185902](https://github.com/user-attachments/assets/02fe6a07-f631-4e84-a92d-d1655bb43ebc)



## Services and Endpoints

### User Service
- Base URL: `http://localhost:3000`
- Endpoints:
  - List Users:
    ```bash
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### Product Service
- Base URL: `http://localhost:3001`
- Endpoints:
  - List Products:
    ```bash
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

---

### Order Service
- Base URL: `http://localhost:3002`
- Endpoints:
  - List Orders:
    ```bash
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### Gateway Service
- Base URL: `http://localhost:3003/api`
- Endpoints:
  - Users:
    ```bash
    curl http://localhost:3003/api/users
    ```
  - Products:
    ```bash
    curl http://localhost:3003/api/products
    ```
  - Orders:
    ```bash
    curl http://localhost:3003/api/orders
    ```

---


### Screenshot: Testing Output

Separate Endpoints:

-![Screenshot 2025-05-10 184251](https://github.com/user-attachments/assets/5ecbda41-cb0f-4ae1-b3d0-a437b067af49)

-![Screenshot 2025-05-10 184806](https://github.com/user-attachments/assets/775788fb-1b6b-4441-91d6-7eaacc4841e8)

-![Screenshot 2025-05-10 184849](https://github.com/user-attachments/assets/8a685b5f-a125-4b65-9224-7855f6dbfbed)



Accessing through gateway service:

-![Screenshot 2025-05-10 184934](https://github.com/user-attachments/assets/ebbf97fa-3cc1-4c64-8896-156a040b25b3)

-![Screenshot 2025-05-10 185001](https://github.com/user-attachments/assets/44c47ce7-fb9f-407d-8015-872ac78f241d)

-![Screenshot 2025-05-10 185116](https://github.com/user-attachments/assets/54c9dcff-693a-4e4e-a05c-1a0495c79af4)



## Common Troubleshooting

| Problem                            | Solution                                                 |
|------------------------------------|----------------------------------------------------------|
| Port already in use                | Stop the conflicting process or change port in compose   |                |
| Docker command not found           | Ensure Docker is installed and in system path            |
| Services cannot talk to each other | Ensure correct `depends_on` and service names are used   |

## Stopping the Application

```bash
docker-compose down
```

-<img width="502" alt="image" src="https://github.com/user-attachments/assets/e3f1bfe4-5b67-4b17-8880-c86b69754cbe" />


### To stop and remove all containers, networks, and volumes:

```bash
docker-compose down -v
```

## Notes

- All services use the same Docker network by default for internal communication.
- Ensure no services are already occupying ports 3000-3003 on your host machine.
- Make sure each Dockerfile correctly installs dependencies and runs the application.
