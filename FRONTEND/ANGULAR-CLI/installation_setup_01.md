To install the Angular CLI, you’ll need **Node.js** and **npm** (Node Package Manager) installed on your system first. Here’s a step-by-step guide:

---

### **1. Check if Node.js is installed**

Open your terminal (Command Prompt, PowerShell, or shell) and run:

```bash
node -v
```

If you see a version number, Node.js is installed. Angular CLI typically works best with **Node.js LTS versions**.
If not installed, download it from: [https://nodejs.org](https://nodejs.org)

---

### **2. Install Angular CLI globally**

Run:

```bash
npm install -g @angular/cli
```

The `-g` flag means **global installation**, so you can use Angular CLI commands anywhere.

---

### **3. Verify installation**

Run:

```bash
ng version
```

You should see the installed Angular CLI version and environment details.

---

### **4. Create a new Angular project (optional)**

To test, you can create a sample app:

```bash
ng new my-app
cd my-app
ng serve
```

Then open [http://localhost:4200](http://localhost:4200) in your browser.

---

Do you want me to also give you **a quick fix guide** for the common "permission denied" error people sometimes get when installing Angular CLI globally? That trips up a lot of first-time installs.
