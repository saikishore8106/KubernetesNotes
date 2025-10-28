# 🧭 Docker & Kubernetes — Developer Notes

## 📘 1. Where Exactly Kubernetes Fits in the Software Lifecycle

Kubernetes is primarily used in the **Deployment**, **Scaling**, and **Operations** stages of the software development lifecycle.

| Stage                        | Description                                  | Tools Commonly Used                     | Kubernetes Role                               |
| ---------------------------- | -------------------------------------------- | --------------------------------------- | --------------------------------------------- |
| **1. Development**           | Writing and building application code        | IDEs, Git, Docker                       | Not directly used                             |
| **2. Build & Test**          | Packaging app into containers and testing    | Docker, CI/CD (Jenkins, GitHub Actions) | Used for test environment automation          |
| **3. Deployment**            | Releasing applications to production/staging | Kubernetes, Helm                        | ✅ Kubernetes manages containerized deployment |
| **4. Scaling & Monitoring**  | Handling user load, ensuring reliability     | Prometheus, Grafana, K8s HPA            | ✅ Kubernetes auto-scales and self-heals apps  |
| **5. Maintenance & Updates** | Continuous updates with minimal downtime     | Rolling Updates, Blue-Green Deployments | ✅ Kubernetes manages smooth rollouts          |

🔹 **In short:**

> Kubernetes comes after the app is containerized — it handles **deployment**, **scaling**, and **maintenance** of containers in production environments.


-----
# Image of SDLC

![image](/assets/kubernetes.png)
---

## 🐳 2. What is Docker?

Docker is a **containerization platform** that allows developers to package applications and their dependencies into lightweight, portable containers.

### 🧩 Key Concepts

* **Container** → Lightweight, isolated environment for running applications.
* **Image** → Blueprint of a container (includes app code, libraries, dependencies).
* **Dockerfile** → Script that defines how to build a Docker image.
* **Docker Engine** → The runtime that builds and runs containers.

### 🧠 Why Use Docker

* Eliminates “*works on my machine*” issues.
* Fast, consistent deployments.
* Lightweight compared to virtual machines.
* Enables microservices architecture.

### 🧱 Example

```bash
# Build Docker image
docker build -t myapp:v1 .

# Run a container
docker run -d -p 8080:80 myapp:v1
```

---

## ⚖️ 3. Difference Between Docker and Kubernetes

| Feature               | Docker                                         | Kubernetes                                            |
| --------------------- | ---------------------------------------------- | ----------------------------------------------------- |
| **Purpose**           | Containerization tool (build & run containers) | Container orchestration tool (manage many containers) |
| **Scope**             | Single container lifecycle                     | Cluster of containers                                 |
| **Scaling**           | Manual (Docker Compose)                        | Automatic (Horizontal Pod Autoscaler)                 |
| **Networking**        | Basic container networking                     | Complex cluster networking                            |
| **Load Balancing**    | Limited                                        | Built-in Service Load Balancer                        |
| **High Availability** | Not built-in                                   | Yes — replicates and replaces failed pods             |
| **Storage**           | Local volumes                                  | Persistent volumes, dynamic storage                   |

🔹 **In summary:**

> Docker creates and runs containers, while **Kubernetes manages, schedules, and scales them across multiple machines**.

---

## ☸️ 4. What is Kubernetes?

Kubernetes (also known as **K8s**) is an **open-source container orchestration platform** developed by Google.
It automates **deployment, scaling, and management** of containerized applications.

### ⚙️ Basic Workflow

1. Developers build Docker images of apps.
2. Push the images to a container registry (e.g., Docker Hub).
3. Kubernetes pulls these images and deploys them as Pods.
4. Kubernetes ensures the app is running, scaled, and healthy.


---

## 🧠 Quick Revision Points

* **Docker** → Packages your app into containers.
* **Kubernetes** → Manages those containers in clusters.
* **Used in Lifecycle:** Mainly during *deployment* and *operations*.
* **Together:** They make app delivery faster, scalable, and reliable.

---

