# 🧩 Kubernetes Core Concepts — kubectl, Pod, Container, and Load Balancer

## 📘 1. `kubectl` — Kubernetes Command Line Tool

* `kubectl` is the **command-line interface (CLI)** used to interact with the **Kubernetes cluster**.
* It communicates with the **Kubernetes API server** to **deploy, manage, inspect, and troubleshoot** cluster resources.

### 🔹 Common `kubectl` Commands

| Command                               | Description                                     |
| ------------------------------------- | ----------------------------------------------- |
| `kubectl get pods`                    | List all running pods                           |
| `kubectl get nodes`                   | Show all cluster nodes                          |
| `kubectl describe pod <pod-name>`     | Show detailed info about a specific pod         |
| `kubectl apply -f deployment.yaml`    | Apply or update configurations from a YAML file |
| `kubectl delete pod <pod-name>`       | Delete a specific pod                           |
| `kubectl logs <pod-name>`             | View container logs inside a pod                |
| `kubectl exec -it <pod-name> -- bash` | Open an interactive shell inside a container    |

---

## 🧱 2. **Container**

* A **container** is a **lightweight, portable unit** that packages:

  * An application
  * Its dependencies
  * Runtime environment
* Containers ensure that the app runs **consistently** across different environments.

### 🐳 Example:

A container might run **Nginx**, **Python**, or **Node.js** inside it using Docker or another container runtime.

---

## ⚙️ 3. **Pod**

* A **Pod** is the **smallest deployable unit in Kubernetes**.
* It **wraps one or more containers** together.
* All containers inside a Pod:

  * Share the **same network namespace** (same IP address and ports)
  * Share **storage volumes**
  * Are **scheduled on the same Node**


---

## 🔍 4. **Difference Between Pod and Container**

| Feature        | Pod                                                | Container                                            |
| -------------- | -------------------------------------------------- | ---------------------------------------------------- |
| **Definition** | Smallest deployable unit in Kubernetes             | A lightweight runtime unit that runs the actual app  |
| **Contains**   | One or more containers                             | Application code + dependencies                      |
| **Managed By** | Kubernetes                                         | Container runtime (Docker, containerd, etc.)         |
| **Networking** | Has its own IP; containers inside share it         | Has its own isolated network namespace if standalone |
| **Purpose**    | Kubernetes abstraction to manage containers easily | Execute an app or process                            |

🧠 **Analogy:**

* A **container** is like a **car** (runs the app).
* A **pod** is like a **garage** that can hold one or more cars (containers) together.

---

## 🌐 5. **Load Balancer in Kubernetes**

* A **LoadBalancer** distributes **network traffic** across multiple Pods or services to ensure:

  * High availability
  * Fault tolerance
  * Efficient resource utilization

### ⚙️ Kubernetes Load Balancer Types

| Type                    | Description                                                                               |
| ----------------------- | ----------------------------------------------------------------------------------------- |
| **ClusterIP** (default) | Exposes service **inside the cluster only**                                               |
| **NodePort**            | Exposes service on a **port of each Node’s IP** (accessible externally)                   |
| **LoadBalancer**        | Exposes service **externally via cloud provider’s load balancer** (e.g., AWS ELB, GCP LB) |
| **Ingress**             | Advanced routing (acts like a Layer 7 load balancer)                                      |
