

---

 **1️⃣ ConfigMap**

### 🔹 **Definition:**

> A **ConfigMap** is used to store **non-sensitive configuration data** (like app settings, environment variables, or URLs) separately from your code.

 **In Simple Words:**

It’s like a **settings file** for your app —
you keep things like database names, API URLs, or configuration values here
so you don’t hardcode them in your application.

 **Why It’s Useful:**

* Keeps your app flexible and easy to update.
* You can change configurations **without rebuilding or redeploying** your app.

 **Example (in plain English):**

You have an Nginx app → instead of writing server name inside the pod,
you store it in a ConfigMap, like:

```
SERVER_NAME = mywebsite.com
```

If tomorrow it changes, you just update the ConfigMap, not the code.

---

 **2️⃣ Secrets**

### 🔹 **Definition:**

> A **Secret** is used to store **sensitive or private data** like passwords, tokens, and API keys — securely.

 **In Simple Words:**

It’s like a **locker** in Kubernetes —
you keep your **passwords or secret keys** inside it,
so they are not visible in plain text.

 **Why It’s Useful:**

* Protects sensitive information (unlike ConfigMap, which is visible).
* Values are **base64-encoded** and can be encrypted.
* Used for connecting to databases, private registries, or APIs securely.

 **Example (in plain English):**

Instead of writing:

```
DB_PASSWORD = admin123
```

inside your app code,
you store it safely inside a **Secret**,
and the app fetches it securely at runtime.

---

 **3️⃣ Annotations**

### 🔹 **Definition:**

> **Annotations** are used to store **extra information or metadata** about Kubernetes objects.

 **In Simple Words:**

Annotations are like **sticky notes** 🗒️ on your Kubernetes objects —
they don’t affect how things work,
but they **help humans or tools** remember important info.

 **Why It’s Useful:**

* Helps teams or monitoring tools identify who created or updated a resource.
* Used by tools like **Helm**, **Prometheus**, or **Ingress controllers**
  to store config details or special instructions.

 **Example (in plain English):**

You can “label” a deployment with:

```
annotation: created-by: Sai
```

This doesn’t change how your pod runs —
but helps others see *who deployed it* or *when it was deployed*.

