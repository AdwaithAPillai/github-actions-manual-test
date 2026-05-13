
# GitHub Actions Manual Trigger Demo

This project demonstrates how to configure and use a manual deployment trigger using GitHub Actions (`workflow_dispatch`).

---

# Project Structure

```bash
.github/
└── workflows/
    └── manual-deploy.yml
```

---

# Prerequisites

Before starting, install:

* Git
* GitHub Account
* VS Code (Optional)

---

# Install Git

Download Git:

https://git-scm.com/download/win

Verify installation:

```bash
git --version
```

Expected Output:

```bash
git version 2.x.x
```

---

# Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/github-actions-manual-test.git
```

Go inside project:

```bash
cd github-actions-manual-test
```

---

# Create Workflow File

Create folders:

```bash
mkdir -p .github/workflows
```

Create workflow:

```bash
touch .github/workflows/manual-deploy.yml
```

---

# GitHub Actions Workflow

Add the following content inside:

```yaml
name: Manual Deployment Test

on:
  workflow_dispatch:

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Print Message
        run: |
          echo "Manual deployment triggered successfully!"
```

---

# Commit and Push

```bash
git add .
git commit -m "Added manual workflow"
git push origin main
```

---

# Run Manual Deployment

In GitHub:

1. Open Repository
2. Go to Actions
3. Select "Manual Deployment Test"
4. Click "Run workflow"
5. Select branch
6. Click green "Run workflow"

---

# Verify Workflow Logs

Open the workflow run and check logs:

```bash
Manual deployment triggered successfully!
```

---

# What is workflow_dispatch?

`workflow_dispatch` is a GitHub Actions trigger that allows workflows to run manually from the GitHub UI.

Example:

```yaml
on:
  workflow_dispatch:
```

---

# Use Cases

* Staging deployment
* Production deployment
* Kubernetes deployment
* ECS deployment
* Rollback deployment
* Terraform apply
* Database migration

---

# Benefits

* Better deployment control
* Reduced GitHub Actions minutes usage
* Prevent accidental deployments
* Supports approval workflows

---

# Author

Adwaith A Pillai
