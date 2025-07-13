# Container-Orchestration-and-Docker-Swarm
# 🐳 Docker Swarm Two-Tier Application Deployment – By Sultan

This project shows how to deploy a simple **two‑tier application** with **Docker Swarm**.

**Services**

| Tier      | Image                               | Replicas |
|-----------|-------------------------------------|----------|
| Backend   | `sultan/two-tier-backend-image:latest` | 3        |
| Frontend  | `sultan/two-tier-frontend-image:v2`    | 3        |

## 🚀 Quick Start

1. **Init Swarm**

   ```bash
   docker swarm init
   ```

2. **Deploy**

   ```bash
   docker stack deploy -c stack.yaml two-tier
   ```

3. **Check**

   ```bash
   docker service ls
   ```

   App is available at **http://localhost:8081**

4. **Remove**

   ```bash
   docker stack rm two-tier
   ```

## ℹ️ stack.yaml

All configuration lives in `stack.yaml` (see file in this repo).

---

_Made with ❤️ by Sultan_
