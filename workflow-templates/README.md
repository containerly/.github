Guide to Using Your Organization's .github Workflow Templates
GitHub Actions allows organizations to centralize and share workflows across multiple repositories using the .github repository. This guide will help you understand how to utilize your organization's shared workflow templates to maintain consistency and efficiency across all your projects.

Table of Contents
Overview of Shared Workflows
Setting Up Shared Workflows
Referencing Shared Workflows in Repositories
Customizing Shared Workflows
Best Practices
Troubleshooting
Additional Resources
Overview of Shared Workflows
Shared workflows are reusable GitHub Actions workflows stored in your organization's .github repository. They enable you to:

Promote Consistency: Ensure all repositories follow the same CI/CD processes.
Simplify Maintenance: Update workflows in one place rather than individually.
Encourage Best Practices: Standardize procedures across projects.
Setting Up Shared Workflows
To create shared workflows:

Create the .github Repository: If not already present, create a repository named .github in your organization's GitHub account.

Add Workflows to the Repository:

Place your workflow files in the .github/workflows/ directory of the .github repository.

For example:

arduino
Copy code
.github/
└── workflows/
    ├── ci.yml
    └── release.yml
Define Workflow Dispatching:

Ensure each workflow file starts with on: workflow_call: to make it reusable.

Example ci.yml:

yaml
Copy code
on:
  workflow_call:
    inputs:
      node-version:
        description: 'Node.js version to use'
        required: false
        default: '16'

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set Up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: ${{ inputs.node-version }}
      - name: Install Dependencies
        run: npm install
      - name: Run Tests
        run: npm test
Referencing Shared Workflows in Repositories
To use a shared workflow in one of your repositories:

Create a Workflow File:

In your repository, create a workflow file under .github/workflows/, such as .github/workflows/ci.yml.
Reference the Shared Workflow:

Use the uses keyword to point to the shared workflow.

Example:

yaml
Copy code
name: Continuous Integration

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    uses: your-org/.github/.github/workflows/ci.yml@main
    with:
      node-version: '18'
Replace your-org with your organization's GitHub name.

Specify Inputs and Secrets:

If the shared workflow requires inputs or secrets, provide them under with: and secrets:.
Customizing Shared Workflows
While shared workflows provide a common foundation, you can customize them for individual repositories:

Override Inputs: Provide different input values as needed.
Add Steps: Include additional steps in your repository's workflow file if necessary.
Extend Jobs: Use the needs keyword to add jobs that depend on the shared workflow.
Example of Adding Additional Steps
yaml
Copy code
name: Continuous Integration

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    uses: your-org/.github/.github/workflows/ci.yml@main
    with:
      node-version: '18'

  deploy:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - name: Deploy Application
        run: ./deploy.sh
Best Practices
Version Pinning: Reference a specific version or tag of the shared workflow to prevent unexpected changes.

Example: uses: your-org/.github/.github/workflows/ci.yml@v1
Document Inputs and Outputs: Clearly document any inputs the workflow accepts and outputs it provides.

Use Descriptive Names: Name your workflows and jobs descriptively to make them easily identifiable.

Secure Secrets: Ensure any required secrets are properly stored in the repository's settings.

Troubleshooting
Workflow Not Found:

Verify the uses path is correct.
Ensure the referenced branch or tag exists.
Input Errors:

Confirm that all required inputs are provided.
Check for typos in input names.
Permission Issues:

Ensure that the repository has access to the .github repository.
Verify that GitHub Actions are enabled for your organization and repository.
Additional Resources
GitHub Documentation:

Reusing Workflows
Sharing Workflows with Your Organization
Community Support:

Participate in your organization's Discussions or reach out to team members for assistance.
Conclusion
By leveraging shared workflow templates in your organization's .github repository, you can:

Streamline CI/CD Pipelines: Reduce setup time for new projects.
Maintain High Standards: Ensure all projects comply with organizational policies.
Facilitate Collaboration: Make it easier for team members to contribute across repositories.
If you have suggestions for improving the shared workflows or need further assistance, please contribute to the .github repository or contact your organization's DevOps team.