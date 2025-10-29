# 🧩 Kubernetes Architecture — Complete Explanation

Kubernetes architecture is based on a **master–worker (control plane–node)** model that manages and runs containerized applications efficiently.
It ensures **scalability, self-healing, and automation** of containerized workloads across a cluster of machines.

---

## 🏗️ High-Level Overview

Kubernetes consists of two main parts:

1. **Control Plane (Master Node)** – The brain of Kubernetes that manages the cluster.
2. **Worker Nodes** – The machines (physical or virtual) that run the actual applications in **Pods**.

Communication between these layers happens via the **Kubernetes API Server**.

---

## 🧠 Control Plane (Master Node)

The **Control Plane** is responsible for maintaining the desired state of the cluster — what applications are running, their configurations, scaling, and availability.

### 🧩 Components of the Control Plane

#### 1. **API Server (`kube-apiserver`)**

* Acts as the **entry point** for all cluster operations.
* Exposes a **REST API** for users, tools, and other components.
* Validates and processes requests (e.g., creating pods, services, deployments).
* Serves as the **communication hub** for all components.

📘 Example:
When you run

```bash
kubectl apply -f app.yaml
```

the request first hits the **API Server**, which stores the configuration in etcd and triggers other control plane components.

---

#### 2. **etcd**

* A **distributed, consistent key–value store** used by Kubernetes to store **cluster state** and **configuration data**.
* Acts as the **single source of truth** for the cluster.
* Uses the **Raft consensus algorithm** for consistency and reliability.

📘 Example:
If a pod crashes, its desired state (stored in etcd) helps Kubernetes recreate it automatically.

---

#### 3. **Controller Manager (`kube-controller-manager`)**

* Ensures that the cluster’s **current state** matches the **desired state** defined by the user.
* Continuously monitors objects via the API Server and makes necessary adjustments.

🧱 Common Controllers:

* **Node Controller** → Monitors node health.
* **Replication Controller** → Maintains correct number of pods.
* **Endpoint Controller** → Manages service endpoints.
* **Namespace Controller** → Handles namespace lifecycle.

📘 Example:
If a pod fails, the Replication Controller creates a new one to maintain the desired number of replicas.

---

#### 4. **Scheduler (`kube-scheduler`)**

* Responsible for **assigning Pods to worker nodes**.
* Evaluates resource availability and policies to make placement decisions.

🔍 Factors considered:

* CPU and Memory availability
* Node affinity or anti-affinity
* Taints and tolerations
* Pod resource requests and limits

📘 Example:
If a new Pod is created, the Scheduler finds a node that has enough free resources to host it.

---

### 🧭 Summary of Control Plane Responsibilities

| Component              | Purpose                               |
| ---------------------- | ------------------------------------- |
| **API Server**         | Gateway for all Kubernetes commands   |
| **etcd**               | Database storing cluster state        |
| **Controller Manager** | Enforces the desired cluster state    |
| **Scheduler**          | Assigns Pods to suitable worker nodes |

---

## ⚙️ Worker Node Architecture

**Worker Nodes** are where the actual application containers run.
Each node has components that communicate with the control plane and ensure containers are healthy.

### 🔹 Components of a Worker Node

#### 1. **Kubelet**

* Agent that runs on every node.
* Communicates with the API Server.
* Ensures that containers (defined in Pod specs) are **running and healthy**.
* Reports node and pod status back to the control plane.

📘 Example:
If a container crashes, **Kubelet** restarts it automatically to maintain pod health.

---

#### 2. **Kube Proxy**

* Handles **networking** for pods.
* Maintains **network rules** to route traffic between pods, services, and external users.
* Implements **load balancing** for services using `iptables` or `IPVS`.

📘 Example:
When multiple pods serve the same application, Kube Proxy distributes network traffic among them.

---

#### 3. **Container Runtime**

* The actual software responsible for running containers.
* Kubernetes supports multiple runtimes through the **Container Runtime Interface (CRI)**.

Common Runtimes:

* **containerd**
* **CRI-O**
* **Docker** (legacy support)

📘 Example:
When the Kubelet starts a pod, the container runtime pulls the image and launches the containers.

---

### 🧭 Summary of Worker Node Responsibilities

| Component             | Function                                    |
| --------------------- | ------------------------------------------- |
| **Kubelet**           | Ensures containers are running as specified |
| **Kube Proxy**        | Handles networking and load balancing       |
| **Container Runtime** | Runs the containers in pods                 |

---

## 🔄 How the Architecture Works Together

Here’s the **workflow** between Control Plane and Worker Nodes:

1. **User Command** → User submits a YAML file (`kubectl apply -f deployment.yaml`).
2. **API Server** → Validates and stores desired state in **etcd**.
3. **Scheduler** → Assigns new Pods to suitable worker nodes.
4. **Kubelet** → Creates and manages containers on assigned node.
5. **Controller Manager** → Monitors and ensures cluster state matches the desired configuration.
6. **Kube Proxy** → Routes traffic between pods and services.
7. **Continuous Reconciliation** → Kubernetes keeps comparing the current state with desired state and self-heals when mismatched.

---
