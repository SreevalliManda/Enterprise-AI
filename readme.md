# 🚀 Project Setup and Contribution Guide

This guide walks you through setting up your development environment using **uv** and contributing changes via **Git**.

---

## 🐍 Python Environment Setup using `uv`

Follow these steps to create and configure your Python virtual environment.

### **1. Pin Python Version**

```bash
uv python pin 3.11.8
```

Pins the Python version to **3.11.8** for the current project.

---

### **2. Create Virtual Environment**

```bash
uv venv --python 3.11.8
```

Creates a virtual environment using the pinned Python version.

---

### **3. Activate Virtual Environment**

```bash
source .venv/Scripts/activate
```

Activates the virtual environment.

> 💡 On Windows PowerShell, use:
>
> ```bash
> .\.venv\Scripts\activate
> ```

---

### **4. Install Required Packages**

```bash
uv pip install langchain==0.3.27 langgraph==0.6.7 langchain-openai==0.3.33 python-dotenv==1.1.1
```

Installs the required libraries for building and running **LangChain** and **LangGraph** projects.

---

### **5. Verify Installation**

```bash
python -c "import importlib.metadata; print(importlib.metadata.version('langgraph'))"
```

Confirms successful installation by checking the `langgraph` version.

---

### **6. Install Jupyter Tools (Optional)**

```bash
uv pip install ipykernel jupyter
```

Adds **Jupyter Notebook** and **IPython kernel** support for interactive notebooks.

---

### ✅ **Environment Ready**

You can now run:

```bash
jupyter notebook
```

or

```bash
python main.py
```

to start working in your configured environment.

---

## 🌿 Git Fork and Pull Request Workflow

Follow these steps to contribute your changes to the original repository.

### **1. Add the Original Repository as “Upstream”**

```bash
git remote add upstream https://github.com/SreevalliManda/Enterprise-AI.git
git remote -v  # to verify
```

This links your local repo to the original repository for syncing future updates.

---

### **2. Create a New Branch for Your Changes**

```bash
git checkout -b feature-update-readme
```

Creates a new branch where you can safely make changes.

---

### **3. Make Your Changes, Commit, and Push**

```bash
git add .
git commit -m "Updated README with setup details"
git push origin feature-update-readme
```

Pushes your new branch and commits to your fork on GitHub.

---

### **4. Open a Pull Request (PR)**

1. Go to your **fork** on GitHub.
2. You’ll see a button:
   👉 **“Compare & pull request”**
3. Click it to open a PR from your branch in your fork → to the **main branch** of the original repo.

---

### **5. Review and Merge**

The repository owner (or you, if you manage both repos) can:

* Review the proposed changes
* Discuss feedback
* Merge once approved ✅

---

