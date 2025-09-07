# Security Analysis Workflow

This repository includes a GitHub Actions workflow that integrates CodeQL security scanning with SecDim learning materials for hands-on vulnerability education.

## What it does

The workflow (`security-analysis.yml`) performs the following steps:

1. **CodeQL Security Scanning**: Analyzes the JavaScript codebase for security vulnerabilities using GitHub's CodeQL engine
2. **Severity Filtering**: Extracts only high and critical severity findings from the SARIF output
3. **SecDim Enhancement**: Uses the [SecDim Sandbox Action](https://github.com/secdim/sandbox-action) to enrich findings with interactive learning labs
4. **Results Upload**: Makes enhanced findings available in the repository's Security tab with learning links attached

## Features

- **Automated Security Analysis**: Runs on every push, pull request, and weekly schedule
- **Severity Focus**: Only processes high and critical vulnerabilities to reduce noise
- **Interactive Learning**: Each vulnerability links to a containerized lab environment
- **Educational Content**: Includes AI-powered hints, real-world exploitation tests, and step-by-step remediation guidance
- **Privacy-First**: Only minimal metadata leaves your repository; source code stays local

## Viewing Results

After the workflow runs:

1. **Security Tab**: View all findings with SecDim learning labs attached
2. **Artifacts**: Download SARIF files for detailed offline analysis
3. **Learning Labs**: Click through to interactive environments for hands-on learning

## SecDim Learning Labs Provide

- Interactive containerized environments for each vulnerability type
- Real attacker simulation tests showing exploitation techniques
- AI-powered hints and validation feedback
- Step-by-step remediation guidance with code examples
- No account required - public labs are freely accessible

## Workflow Triggers

- **Push**: Runs on pushes to `main` or `master` branches
- **Pull Request**: Runs on pull requests targeting `main` or `master` branches  
- **Schedule**: Runs weekly on Sundays at 2 AM UTC for continuous monitoring

## Privacy and Security

- Your source code never leaves your GitHub environment
- Only rule metadata (like CWE IDs) is used for lab matching
- All processing happens within your CI runner
- SecDim only receives minimal search queries to match vulnerabilities with appropriate learning content