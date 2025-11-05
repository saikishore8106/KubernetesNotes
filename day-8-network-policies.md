
## 🕸️ **Network Policies**

**Definition:**
A **Network Policy** defines **rules that control communication** between Pods or between Pods and external systems.

**Key Points:**

* By default, **all Pods can talk to each other** — Network Policies change that.
* You can restrict traffic **based on labels, ports, or IP ranges**.
* They improve **security** by isolating workloads (e.g., frontend can talk to backend, but not directly to the database).
* Often compared to **firewalls for Pods** inside the Kubernetes network.

💡 *Think of it like defining who can call whom on a private phone network.*

---
