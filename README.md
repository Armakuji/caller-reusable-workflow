# Caller Reusable Workflow

This repository demonstrates how to call and use reusable GitHub Actions workflows from another repository.

## Overview

This project showcases the implementation of a caller workflow that invokes a reusable workflow from the `Armakuji/reusable-workflow` repository. It's designed to help developers understand how to:

- Call external reusable workflows
- Pass secrets between workflows
- Chain workflow jobs with dependencies

## Workflow Structure

The main workflow file is located at `.github/workflows/demo.yaml` and contains:

### Jobs

1. **echo-start**: A simple job that runs on Ubuntu and echoes the trigger event
2. **call-workflow-passing-data**: Calls the reusable workflow after the first job completes

### Key Features

- **Trigger**: Runs on every push to the repository
- **Dependencies**: The second job depends on the completion of the first job
- **Secret Passing**: Demonstrates how to pass secrets to reusable workflows
- **External Workflow**: Uses a reusable workflow from `Armakuji/reusable-workflow@main`

## Configuration

### Required Secrets

This workflow requires the following secret to be configured in your repository:

- `CALLER_TOKEN`: A token that will be passed to the reusable workflow

### Setting Up Secrets

1. Go to your repository's Settings
2. Navigate to Secrets and variables → Actions
3. Click "New repository secret"
4. Add `CALLER_TOKEN` with your desired value

## Usage

1. Clone this repository
2. Configure the required secrets (see Configuration section)
3. Push changes to trigger the workflow
4. Monitor the workflow execution in the Actions tab

## Workflow Flow

```
Push Event → echo-start → call-workflow-passing-data → Reusable Workflow
```

## Files Structure

```
.
├── .github/
│   └── workflows/
│       └── demo.yaml          # Main workflow file
└── README.md                  # This file
```

## Learning Objectives

This repository helps you understand:

- How to structure caller workflows
- Passing secrets to reusable workflows
- Setting up job dependencies
- Working with external reusable workflows

## References

- [GitHub Actions Reusable Workflows Documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows)
- [GitHub Actions Secrets Documentation](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Contributing

Feel free to fork this repository and experiment with different workflow configurations to better understand GitHub Actions reusable workflows.