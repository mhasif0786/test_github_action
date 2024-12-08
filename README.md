# **GitHub Actions Workflow: Run Python Code**

This repository demonstrates a GitHub Actions workflow for running Python scripts automatically. The workflow is defined in a YAML file stored in the .github/workflows/ directory.

# Workflow File Location

The workflow file is located at:

# Copy code
.github/workflows/run-python-code.yml

Workflow Details
Workflow Name

name: Run Python Code
The workflow is named "Run Python Code" to indicate its purpose.
Trigger Events
on:
  push:
    branches:
      - main
  pull_request:
push: The workflow is triggered whenever code is pushed to the main branch.
pull_request: It also runs when a pull request is opened.
Jobs
Job 1: Run Python Code
jobs:
  run-python-code:
    runs-on: ubuntu-latest
    environment: Production
jobs: Defines the tasks to perform.
run-python-code: The name of the job.
runs-on: Specifies the environment where the job runs (ubuntu-latest).
environment: The job requires approval to deploy in the Production environment.

# Steps Breakdown
1. Checkout Repository

- name: Checkout code
  uses: actions/checkout@v3
This step uses the checkout action to fetch the repository’s code.
2. Set Up Python Environment
- name: Set up Python
  uses: actions/setup-python@v4
  with:
    python-version: '3.x'
The setup-python action configures the workflow to use Python version 3.x.
3. Run Python Script
- name: Run Python script
  run: |
    python app.py
Executes the Python script app.py in the repository.

# How to Add This Workflow
Step 1: Create the Workflow File
Navigate to your repository.
Create the following directory structure:
.github/workflows/
Inside the workflows folder, create a file named run-python-code.yml.
# Step 2: Add the YAML Code
Copy and paste the following into run-python-code.yml:
name: Run Python Code

on:
  push:
    branches:
      - main
  pull_request:

jobs:
  run-python-code:
    runs-on: ubuntu-latest
    environment: Production

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.x'

    - name: Run Python script
      run: |
        python app.py

# Step 3: Push Your Workflow to GitHub
Commit and push your changes to the repository:


git add .github/workflows/run-python-code.yml
git commit -m "Add workflow to run Python code"
git push origin main
# How It Works
Trigger: The workflow runs when code is pushed to the main branch or a pull request is created.
Execution: It checks out the code, sets up Python, and runs the app.py script.
View Logs: Navigate to the Actions tab in your GitHub repository to see the workflow's progress and output.
Extending the Workflow
.
