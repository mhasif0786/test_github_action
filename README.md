# **GitHub Actions Workflow: Run Python Code**

This repository demonstrates a GitHub Actions workflow for running Python scripts automatically. The workflow is defined in a YAML file stored in the .github/workflows/ directory.

# Workflow File Location

The workflow file is located at:
.github/workflows/run-python-code.yml


# How to Add This Workflow
Step 1: Create the Workflow File
Navigate to your repository.
Create the following directory structure:
.github/workflows/
Inside the workflows folder, create a file named run-python-code.yml.

# Step 2: Add the YAML Code
Copy and paste the following into run-python-code.yml:

```
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
```

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
# Navigate to Actions and click on Review deployments
![Pasted Graphic](https://github.com/user-attachments/assets/f7432210-1c21-4f8e-9953-ab8e66b02908)
# Select Production and approve and deploy(In yml we added environment: Production because of this its asking for approval)
![Review pending deployments](https://github.com/user-attachments/assets/0d20618f-f7d9-4d38-b754-f97128e8c6f4)
# Finally workflow executed and we can see the result
![Pasted Graphic 2](https://github.com/user-attachments/assets/c0400f30-c80a-4ab8-b70d-30c6acef9a55)


