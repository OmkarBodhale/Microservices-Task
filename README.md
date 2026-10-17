# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```

---

##Instructions to build Docker images for each service:
1. User Service (Port 3000)
2. Product Service (Port 3001)
3. Gateway Service (Port 3003)

**Run the below Docker commands to create and test each service docker file individually
   Command to create Docker Images
   ```
   docker build -t user-service:v1.0 .\Microservices\user-service\.
   docker build -t product-service:v1.0 .\Microservices\product-service\.
   docker build -t gateway-service:v1.0 .\Microservices\gateway-service\.
   ```
  Commands to get Docker Container running using specific Docker Image
     
     ```
     docker run -p 3000:3000 -d --name user-service user-service:v1.0 
     docker run -p 3001:3001 -d --name product-service product-service:v1.0
     docker run -p 3003:3003 -d --name gateway-service gateway-service:v1.0 
     ```
  Verify whether each container running in Docker Desktop
  <img width="1917" height="985" alt="image" src="https://github.com/user-attachments/assets/67d726c4-8c28-4137-bb74-d0145a0d350e" />

  Verify Individual service running in the browser:
  <img width="1917" height="221" alt="image" src="https://github.com/user-attachments/assets/e0cb8d4d-468b-494a-bb9b-3000f55368cf" />
  <img width="1917" height="267" alt="image" src="https://github.com/user-attachments/assets/aa1f4fcb-6b33-437b-a66a-45cb208e740b" />
  <img width="1917" height="262" alt="image" src="https://github.com/user-attachments/assets/8bb8629e-fc7c-4169-a820-78f9764e4cbc" />




## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker compose -f .\docker-compose.yml up -d
   ```
2. Once the services are running, use the above endpoints to verify the functionality.
   <img width="1902" height="916" alt="image" src="https://github.com/user-attachments/assets/c1d0653c-fff9-4a3f-b67b-960f91440bd5" />
  <img width="1917" height="221" alt="image" src="https://github.com/user-attachments/assets/e0cb8d4d-468b-494a-bb9b-3000f55368cf" />
  <img width="1917" height="267" alt="image" src="https://github.com/user-attachments/assets/aa1f4fcb-6b33-437b-a66a-45cb208e740b" />
  <img width="1917" height="262" alt="image" src="https://github.com/user-attachments/assets/8bb8629e-fc7c-4169-a820-78f9764e4cbc" />
Happy testing!
