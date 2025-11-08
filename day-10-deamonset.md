



 **In Simple Words:**

It’s like saying —
“Run **one helper pod** on every machine (node) in my cluster.”

So if you have 3 nodes → it creates 3 pods (one on each node).
If a new node is added → Kubernetes automatically runs a new pod there too.

---

 **Purpose / Why It’s Used:**

DaemonSets are used for **system-level background tasks** that must run on **every node**, such as:

* 🪵 **Log collection** (e.g., Filebeat, Fluentd)
* 📊 **Monitoring** (e.g., Datadog Agent, Prometheus Node Exporter)
* 🔒 **Security tools** (e.g., Falco)
* 🌐 **Network plugins** (e.g., Calico, Flannel)

---

## ⚙️ **Key Features:**

* Automatically runs **one pod per node**
* Adds pods to **new nodes automatically**
* Deletes pods from **removed nodes automatically**
* Perfect for **background agents**

---

## 🧾 **Example (Easy to Remember):**

If you deploy a DaemonSet for log collection:

```
Node 1 → log-collector-pod
Node 2 → log-collector-pod
Node 3 → log-collector-pod
```

✅ Each pod collects logs from its own node.

---

## 🧱 **Comparison with Deployment:**

| Feature              | **DaemonSet**                | **Deployment**       |
| -------------------- | ---------------------------- | -------------------- |
| Pods per Node        | One per node                 | Multiple on any node |
| Purpose              | System-level background jobs | App-level services   |
| Auto-add on new node | Yes                          | No                   |
| Examples             | Filebeat, Datadog            | Nginx, MySQL         |

---

## 🎯 **One-Line Summary:**

> A **DaemonSet** runs one pod on every node for background system tasks like logging, monitoring, and securit

