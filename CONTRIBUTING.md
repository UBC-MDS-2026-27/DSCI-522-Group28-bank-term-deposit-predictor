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
   - Python, uv, and Quarto versions
   - Operating System (Windows, macOS, Linux)
   - Key library versions (e.g., `pandas`, `scikit-learn`, `matplotlib`)
3. **Steps to Reproduce**: List exact steps to reproduce the error, including data inputs or script execution commands.
4. **Expected vs. Actual Behavior**: Describe what you expected to happen versus what actually occurred.
5. **Traceback / Error Log**: Copy and paste the full error traceback inside a fenced code block.

---

## How to Suggest a Feature or Improvement

Ideas for model improvements, novel feature engineering techniques, new evaluation metrics, or EDA visualizations are very welcome!

To suggest a change:
1. Open a new issue with the title prefix `[Feature Suggestion]: <Brief Title>`.
2. Explain the rationale behind the feature (e.g., handling class imbalance in subscription data, comparing classification thresholds).
3. Outline potential implementation details or data requirements.
4. Discuss the suggestion with maintainers before starting work on major pull requests.

---

## Development Setup

1. Install Git, uv 0.13.9, and Quarto 1.10.18 as described in the [README](README.md).
2. Clone the team repository.

   ```bash
   git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group28-bank-term-deposit-predictor.git
   cd DSCI-522-Group28-bank-term-deposit-predictor
   ```

3. Install the locked Python 3.14 dependencies from the repository root.

   ```bash
   uv sync --locked --python 3.14
   ```

4. Render the report from the repository root.

   ```bash
   uv run --locked quarto render reports/bank_term_deposit_predictor.qmd --to html
   ```

   Rendering downloads the public Bank Marketing dataset from the UCI Machine Learning Repository, writes `data/raw/bank_marketing.csv`, and generates the train and test splits in `data/processed/`. An internet connection is required for the download. Open `reports/bank_term_deposit_predictor.html` to inspect the result.

---

## Workflow for Submitting Changes

Team members work on branches in the shared repository and submit changes through pull requests.

1. **Create a branch from the latest `main`.**

   ```bash
   git switch main
   git pull --ff-only origin main
   git switch -c fix/report-metrics
   ```

2. **Make and verify your changes.** The Quarto source and rendered HTML live in `reports/`. If you change the analysis or report, render it again and review the HTML before committing.
3. **Commit with a descriptive message.** For example, use `fix: Compute report metrics inline`.
4. **Push your branch to the team repository.**

   ```bash
   git push -u origin fix/report-metrics
   ```

5. **Open a pull request into `main`.** In the description, summarize what changed, explain why, list what you verified, and link any related issues. Ask a teammate to review the pull request before merging.

---

## Code and Data Standards

- Follow PEP 8 for Python code. Keep the report's analysis easy to follow.
- The project tracks the public UCI Bank Marketing CSV in `data/raw/`. Keep its source and filename consistent with the report. Keep confidential data and personally identifiable information out of the repository.
- Use `random_state=522` for the report's stratified train/test split so contributors can reproduce the same rows. Explain intentional changes to the split in the pull request.
- If you change a Python dependency, update `pyproject.toml` and `uv.lock` together.

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

Thank you for contributing to the Bank Term Deposit Predictor project! If you have any questions, feel free to open a discussion issue.
