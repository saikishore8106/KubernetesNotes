
## 🌐 **Ingress**

**Definition:**
Ingress is a **Kubernetes resource that manages external HTTP/HTTPS access** to Services inside the cluster.
It acts as a **smart router** that directs incoming requests to the right Service based on the **URL path or domain name**.

**Key Points:**

* Reduces the need for multiple LoadBalancers — one Ingress can handle many Services.
* Can route requests like `example.com/shop` → shop-service and `example.com/blog` → blog-service.
* Supports **SSL/TLS (HTTPS)** termination for secure traffic.
* Controlled by an **Ingress Controller** (like NGINX, Traefik, etc.) which actually does the routing.

💡 *Think of Ingress as your building’s main reception desk — it decides which room (Service) visitors should go to.*

---
