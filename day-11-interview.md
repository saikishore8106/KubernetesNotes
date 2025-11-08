

---

# ☸️ **Top Kubernetes Interview Questions (with Simple Explanations)**

---

## 🧱 **BASIC LEVEL — (For Freshers / Entry-level DevOps)**

| #   | Question                                              | Simple Explanation                                                                                                      |
| --- | ----------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| 1️⃣ | What is Kubernetes?                                   | It’s a container orchestration tool used to automate deployment, scaling, and management of containerized applications. |
| 2️⃣ | What is a Pod?                                        | The smallest deployable unit in Kubernetes — it runs one or more containers together.                                   |
| 3️⃣ | What is a Node?                                       | A machine (VM or physical) where Kubernetes runs pods.                                                                  |
| 4️⃣ | What is a Cluster?                                    | A group of nodes controlled by one master (control plane).                                                              |
| 5️⃣ | What is a Deployment?                                 | It manages multiple replicas of pods and handles rolling updates & rollbacks.                                           |
| 6️⃣ | What is a Service in Kubernetes?                      | It exposes pods to network traffic using labels & selectors.                                                            |
| 7️⃣ | What is a Namespace?                                  | Logical grouping inside a cluster for resource isolation.                                                               |
| 8️⃣ | What is `kubectl`?                                    | The command-line tool used to interact with the Kubernetes cluster.                                                     |
| 9️⃣ | What is a ReplicaSet?                                 | It ensures a specific number of pod replicas are always running.                                                        |
| 🔟  | What is the difference between Docker and Kubernetes? | Docker creates and runs containers; Kubernetes manages and scales containers.                                           |

---

## ⚙️ **INTERMEDIATE LEVEL — (For 1–2 Years Experience)**

| #   | Question                                                         | Simple Explanation                                                                     |
| --- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| 1️⃣ | What is the role of the API Server?                              | It acts as the entry point to the cluster — all commands go through it.                |
| 2️⃣ | What is the role of the Scheduler?                               | It decides on which node a new pod will run.                                           |
| 3️⃣ | What is the role of the Kubelet?                                 | It runs on every node and manages pod life cycles.                                     |
| 4️⃣ | What is ETCD?                                                    | A key-value store that saves the cluster’s state (like a database).                    |
| 5️⃣ | What are ConfigMaps and Secrets?                                 | ConfigMaps store non-sensitive data; Secrets store sensitive data (like passwords).    |
| 6️⃣ | What is a DaemonSet?                                             | Ensures one pod runs on every node (e.g., for logging or monitoring).                  |
| 7️⃣ | What is a StatefulSet?                                           | Manages stateful applications (like databases) that need stable storage or identities. |
| 8️⃣ | What is a Job and CronJob?                                       | Job runs a task once until success; CronJob runs it on a schedule (like a cron).       |
| 9️⃣ | What is a PersistentVolume (PV) and PersistentVolumeClaim (PVC)? | PV = actual storage; PVC = request for that storage by a pod.                          |
| 🔟  | What is a StorageClass?                                          | It defines *how* storage should be provisioned automatically (e.g., EBS in AWS).       |

---

## 🧠 **ADVANCED LEVEL — (For 3+ Years / Real-time Scenarios)**

| #   | Question                                            | Simple Explanation                                                                                                 |
| --- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| 1️⃣ | What is an Ingress?                                 | A resource that exposes HTTP/HTTPS traffic to internal services using one external IP or domain.                   |
| 2️⃣ | What is an Ingress Controller?                      | The actual component that processes ingress rules (like NGINX Ingress Controller).                                 |
| 3️⃣ | How does Kubernetes handle networking between pods? | Each pod gets its own IP; they communicate using CNI (Container Network Interface) plugins like Calico or Flannel. |
| 4️⃣ | How does Kubernetes achieve high availability (HA)? | By running multiple control plane nodes and distributing workloads.                                                |
| 5️⃣ | What is RBAC?                                       | Role-Based Access Control — used to define user permissions in the cluster.                                        |
| 6️⃣ | What are Labels and Selectors?                      | Labels are key-value pairs to tag resources; Selectors help Services or Deployments find those resources.          |
| 7️⃣ | What happens when a pod fails?                      | The ReplicaSet (under Deployment) automatically creates a new pod to replace it.                                   |
| 8️⃣ | How do you scale a deployment?                      | Using `kubectl scale deployment <name> --replicas=<number>` or autoscaling (HPA).                                  |
| 9️⃣ | How do you perform a rolling update and rollback?   | Use `kubectl rollout` commands. It updates pods one by one without downtime.                                       |
| |

