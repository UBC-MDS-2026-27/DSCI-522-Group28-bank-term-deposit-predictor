# Contributing to Bank Term Deposit Predictor Project

Thank you for your interest in contributing to our Bank Term Deposit Predictor project! We welcome contributions from the community, whether you are fixing a bug, adding new features, improving data preprocessing pipelines, or enhancing documentation.

Please read through these guidelines before contributing to ensure a smooth collaboration process.

---

## Table of Contents
1. [Code of Conduct](#code-of-conduct)
2. [How to Report a Bug](#how-to-report-a-bug)
3. [How to Suggest a Feature or Improvement](#how-to-suggest-a-feature-or-improvement)
4. [Development Setup](#development-setup)
5. [Workflow for Submitting Changes](#workflow-for-submitting-changes)
6. [Code and Data Standards](#code-and-data-standards)
7. [Generative AI Usage Policy](#generative-ai-usage-policy)

---

## Code of Conduct

We aim to foster an open, respectful, and inclusive environment. Please treat all contributors with respect, deliver constructive feedback, and maintain a collaborative spirit.

---

## How to Report a Bug

Before creating a bug report, please check the project's **Issues** tab to see if the issue has already been reported. 

If you find a new bug, please open a new Issue using the following guidelines:

1. **Title**: Provide a clear, descriptive title.
2. **Environment**: Include details about your setup:
   - Python version (e.g., Python 3.10)
   - Operating System (Windows, macOS, Linux)
   - Key library versions (e.g., `pandas`, `scikit-learn`, `xgboost`)
3. **Steps to Reproduce**: List exact steps to reproduce the error, including data inputs or script execution commands.
4. **Expected vs. Actual Behavior**: Describe what you expected to happen versus what actually occurred.
5. **Traceback / Error Log**: Copy and paste the full error traceback inside code blocks (\`\`\`).

---

## How to Suggest a Feature or Improvement

Ideas for model improvements, novel feature engineering techniques, new evaluation metrics, or EDA visualizations are very welcome!

To suggest a change:
1. Open a new issue with the title prefix `[Feature Suggestion]: <Brief Title>`.
2. Explain the rationale behind the feature (e.g., handling class imbalance in subscription data, trying a new classifier like LightGBM).
3. Outline potential implementation details or data requirements.
4. Discuss the suggestion with maintainers before starting work on major pull requests.

---

## Development Setup

Follow these steps to set up your local development environment:

1. **Fork and Clone the Repository**:
   ```bash
   git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group28-bank-term-deposit-predictor.git
   cd DSCI-522-Group28-bank-term-deposit-predictor
   ```

2. **Create a Virtual Environment**:
   ```bash
   # Create a virtual environment using uv
   uv venv

   # Activate the environment
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. **Install Dependencies**:
   ```bash
   # Sync environment with pyproject.toml and uv.lock
   uv sync
   ```

4. **Prepare Data**:
   Ensure the banking dataset is placed in the designated `data/raw/` directory (do not commit raw user data to version control).

---

## Workflow for Submitting Changes

All contributions are handled via Git branches and Pull Requests (PRs).

### 1. Create a Topic Branch
Create a branch with a descriptive name off `main`:
```bash
git checkout -b feature/smote-imbalance-handling
# or
git checkout -b fix/data-preprocessing-nulls
```

### 2. Make Your Changes
- Write clean, modular Python code.
- Ensure scripts under `analysis/` are well-documented.

### 3. Commit Guidelines
Write meaningful, concise commit messages:
- Good: `feat: Add SMOTE resampling to handles target class imbalance`
- Good: `fix: Correct target column encoding in preprocessing pipeline`
- Avoid: `updated code` or `fixed stuff`

### 4. Push and Open a Pull Request
1. Push your branch to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```
2. Navigate to the original repository on GitHub and click **Compare & Pull Request**.
3. Fill out the PR template, detailing what changes were made and why.
4. Link any related issues (e.g., `Closes #12`).

---

## Code and Data Standards

- **Code Formatting**: Follow standard **PEP 8** guidelines for Python code. Use `black` or `flake8` for formatting where applicable.
- **Data Privacy**: Never commit sensitive or raw personal banking datasets containing PII (Personally Identifiable Information) directly to GitHub. Use `.gitignore` to keep raw data files out of version control.
- **Reproducibility**: Set random seeds (`random_state=42`) across all stochastic operations (e.g., train-test splits, model initialization, cross-validation).

---

## Generative AI Usage Policy

We recognize that Generative AI tools (e.g., ChatGPT, GitHub Copilot, Claude) can assist in software development and data science workflows. However, to maintain academic/professional integrity, security, and quality control, all contributors must adhere to the following policy:

### 1. Allowed vs. Prohibited Uses
- **Allowed**: Using AI tools as an assistant for ideation, debugging error messages, generating boilerplate code, or drafting initial documentation.
- **Prohibited**: Relying on AI agents to automatically generate entire models, pipeline scripts, or analytical conclusions without human oversight and thorough testing.

### 2. Human Responsibility & Review
- **You are 100% responsible** for all code, data science methodologies, documentation, and analysis you submit.
- You must personally review, test, and understand all code generated or suggested by AI tools.
- Submissions containing AI-generated hallucinations, broken logic, unverified data conclusions, or licensing violations will be closed.

### 3. Mandatory Disclosure
If you used Generative AI tools to significantly generate or refactor code, notebooks, or documentation for a contribution, you **must disclose it in your Pull Request description**:
> **AI Usage Disclosure**: *I used [Tool Name, e.g., ChatGPT / Copilot] to help draft [specific module/functionality]. I have thoroughly verified, tested, and audited all submitted code.*

### 4. Human-Driven Governance
- **Pull requests and issues must be opened, reviewed, authored, and merged by human contributors, NOT by automated AI agents.**
- Automated PR creation bots or AI agent submissions are strictly prohibited.
- Code review discussions must be conducted between human maintainers and human authors.

---

Thank you for contributing to the Bank Subscription Classification project! If you have any questions, feel free to open a discussion issue.