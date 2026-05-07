# MERN Docker Deployment

Production-ready MERN stack application containerized using Docker and deployed on AWS EC2 using modern DevOps practices.

---

## Project Overview

This project demonstrates how to deploy a full-stack MERN application using:

- Docker containerization
- Multi-container architecture
- Docker Compose orchestration
- AWS EC2 deployment
- Nginx reverse proxy configuration
- Environment-based configuration
- Production-ready infrastructure setup

The application itself is intentionally kept simple so the primary focus remains on Docker, deployment, and DevOps workflows.

---

## Features

- React + Vite + TypeScript frontend
- Express + TypeScript backend
- MongoDB Atlas integration
- Product management API
- Health monitoring route
- Dockerized frontend and backend
- Docker Compose setup
- AWS EC2 deployment workflow
- Nginx reverse proxy support

---

## Tech Stack

### Frontend
- React
- Vite
- TypeScript

### Backend
- Node.js
- Express.js

### Database
- MongoDB Atlas

### DevOps / Deployment
- Docker
- Docker Compose
- Nginx
- AWS EC2
- GitHub

---

## AWS EC2 Deployment

This project is designed for deployment on an AWS EC2 Ubuntu server.

### Recommended EC2 Configuration

- Ubuntu Server 22.04 LTS
- t2.micro instance
- 1 vCPU
- 1 GB RAM

### AWS Services Used

- EC2 for hosting containers
- Security Groups for port access
- Elastic IP (optional)
- SSH access for deployment

---

## Project Structure

```txt
mern-docker-deployment/
│
├── client/
│   ├── nginx/
│   ├── src/
│   ├── public/
│   ├── Dockerfile
│   └── ...
│
├── server/
│   ├── src/
│   ├── Dockerfile
│   └── ...
│
├── docker-compose.yml
├── .gitignore
└── README.md
```


## Backend Setup

```bash
cd server
npm install
npm run dev
```

Create `server/.env`

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
```

---

## Frontend Setup

```bash
cd client
npm install
npm run dev
```

Create `client/.env`

```env
VITE_API_URL=http://localhost:5000
```

---

## Docker Setup

Build and start containers:

```bash
docker compose up --build
```

Run in detached mode:

```bash
docker compose up -d
```

Stop containers:

```bash
docker compose down
```

---

## AWS EC2 Deployment Steps

### 1. Connect to EC2 Instance

```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

---

### 2. Install Docker

```bash
sudo apt update
sudo apt install docker.io docker-compose -y
```

Enable Docker:

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

---

### 3. Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/mern-docker-deployment.git
```

---

### 4. Navigate to Project

```bash
cd mern-docker-deployment
```

---

### 5. Start Containers

```bash
docker compose up -d --build
```

---

## Security Group Configuration

Allow these inbound ports:

- 22 → SSH
- 80 → HTTP
- 443 → HTTPS
- 3000 / 5000 (optional during development)

---

## API Routes

- `GET /api/health`
- `GET /api/products`
- `POST /api/products`
- `DELETE /api/products/:id`

---

## Sample Product Payload

```json
{
  "name": "Black Hoodie",
  "price": 1499,
  "category": "Clothing"
}
```

## Author

Viraj
```

