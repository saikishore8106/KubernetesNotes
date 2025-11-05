
## 🔐 **RBAC (Role-Based Access Control)**

**Definition:**
RBAC controls **what actions users or applications can perform** in a Kubernetes cluster.
It defines permissions for **who can access which resources** and what they can do with them.

**Purpose:**

* To prevent unauthorized access or accidental changes.
* To assign roles based on responsibility (developer, admin, CI/CD bot, etc.).

---

### 👤 **Role**

* Defines a **set of permissions** for resources **within one namespace**.
* Example: allow reading Pods or creating ConfigMaps only in the “dev” namespace.
* Used when access control is limited to a specific area of the cluster.

---

### 🔗 **RoleBinding**

* **Assigns a Role** to a specific **user, group, or service account**.
* Connects permissions (Role) with the entity that can use them.
* Works only within that namespace.

💡 *Role = rulebook; RoleBinding = giving that rulebook to someone.*

---

### 🌍 **ClusterRole**

* Like a Role but **works across all namespaces**.
* Used for **cluster-wide resources** like nodes, persistent volumes, or for admins who need full access.
* Common for managing security, monitoring, or system-level functions.

---

### 🌐 **ClusterRoleBinding**

* **Assigns a ClusterRole** to a user or service account across the **entire cluster**.
* Gives cluster-level permissions — very powerful, so use carefully.

💡 *ClusterRole = global rulebook; ClusterRoleBinding = giving global access to someone.*

---
