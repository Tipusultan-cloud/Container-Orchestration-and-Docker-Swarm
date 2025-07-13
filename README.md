🐳 Docker Swarm Two-Tier Application Deployment
This project demonstrates how to deploy a simple two-tier application using Docker Swarm — a native container orchestration tool built into Docker.

The stack includes:

🛠️ A backend service (Node.js, Python, etc.)

🌐 A frontend service (React, Angular, etc.)

Both are deployed in multiple replicas to achieve high availability and load balancing.

📦 What is Docker Swarm?
Docker Swarm is a clustering and orchestration tool for Docker containers. It lets you deploy, scale, and manage services across a group of Docker hosts (nodes) as a single virtual system.

Key features:

🔁 Service Replication: Run multiple replicas of your app.

⚖️ Load Balancing: Distributes requests across containers.

💥 Self-healing: If a container fails, Swarm restarts it.

🔐 Built-in security: TLS by default.

📁 Project Structure
bash
Copy
Edit
stack.yaml    # Docker Swarm stack definition file
README.md     # You're reading it 😊
🚀 Deployment Instructions
1. Initialize Docker Swarm
bash
Copy
Edit
docker swarm init
This makes your machine the Swarm Manager.

2. Create stack.yaml
yaml
Copy
Edit
version: "3"
services:
  backend-service:
    image: zihadbappy/two-tier-backend-image:latest
    deploy:
      replicas: 3

  frontend:
    image: zihadbappy/two-tier-frontend-image:v2
    deploy:
      replicas: 3
    ports:
      - 8081:80
3. Deploy the Stack
bash
Copy
Edit
docker stack deploy -c stack.yaml two-tier
4. Verify the Services
bash
Copy
Edit
docker service ls
View individual service tasks:

bash
Copy
Edit
docker service ps two-tier_frontend
docker service ps two-tier_backend-service
Access frontend in browser:
http://localhost:8081

🧼 To Remove the Stack
bash
Copy
Edit
docker stack rm two-tier
🧠 Why Use Swarm for Two-Tier Apps?
Separates frontend and backend for better scalability

Allows independent deployment and scaling

Enables rolling updates and self-healing

Great for learning orchestration concepts before moving to Kubernetes
