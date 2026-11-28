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

Follow [How to run the analysis](README.md#how-to-run-the-analysis) to set up your SSH key and pull the Docker image. Run the Docker Compose commands below from the repository root on your computer.

### Before your first connection

1. Install [Positron](https://positron.posit.co/download.html). It includes Remote SSH.
2. Check your Git name and email on your computer.

   ```bash
   git config --global user.name
   git config --global user.email
   ```

   Set any missing value with the matching command below. Use your name and the email associated with your GitHub account.

   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

### Work in the container

1. Start the container and check that `analysis-env` is running.

   ```bash
   docker compose up -d
   docker compose ps
   ```

2. In Positron, open the Command Palette (`Cmd+Shift+P` on Mac or `Ctrl+Shift+P` on Windows). Choose **Remote SSH: Show Remote Menu**, select **Connect to Host**, and enter `root@localhost:2222`. If prompted, select **Linux** and confirm the host fingerprint.
3. In the connected Positron window, choose **Open Folder** and enter `/workspace`.
4. Open the interpreter menu, choose **New Console Session**, and select `/opt/venv/bin/python`. If it is missing from the list, open **Python: Select Interpreter** in the Command Palette, choose **Enter interpreter path…**, and enter `/opt/venv/bin/python`. In the Python console, run `import sys` and then `print(sys.executable)` to confirm that it prints `/opt/venv/bin/python`.
5. Use the Terminal, Console, and Render button in the connected Positron window. They run inside the container.
6. When you finish, close the remote Positron window. In a terminal on your computer, run this command from the repository root.

   ```bash
   docker compose down
   ```

### Troubleshoot the connection

- **`~/.ssh/id_ed25519.pub` is a directory.** Run `docker compose down`, remove the directory Docker created, and create the key using the README steps. Then start the container again.
- **`~/.gitconfig` is a directory.** Run `docker compose down`, remove the directory Docker created, and set your Git name and email before restarting. If Git cannot identify you inside the container, check those settings on your computer.
- **SSH asks for a password.** Check that your public key is at `~/.ssh/id_ed25519.pub` and matches the path in `docker-compose.yml`.
- **SSH reports that the host identification changed.** Run `ssh-keygen -R "[localhost]:2222"` on your computer and reconnect.
- **GitHub asks you to sign in during a push.** Complete the sign-in in the browser that Positron opens.
- **SSH rejects the mounted key on Linux because of its ownership.** Uncomment the `StrictModes no` line in the `Dockerfile` and push the change so GitHub Actions builds an updated image.
- **Port `2222` is already in use.** Change the first port in `"2222:22"` in `docker-compose.yml` and connect using the new port.

### Add or update a Python package

1. Create a branch. In the Positron terminal inside the container, run the following command with the package name and exact version. To update an existing package, use its current package name and the new version you want to pin.

   ```bash
   uv add "PACKAGE==VERSION"
   ```

2. Commit `pyproject.toml` and `uv.lock` together and push the branch. Wait for GitHub Actions to publish the new Docker image and update its tag in `docker-compose.yml` on your branch.
3. From the repository root on your computer, with the same branch checked out, run:

   ```bash
   git pull
   docker compose pull
   ```

4. Open a pull request. After it merges and the workflow on `main` finishes, teammates on `main` run `git pull` and `docker compose pull` to get the updated image.

### Republish the report

Rerender the report using the [README instructions](README.md#3-render-the-report). From the repository root, copy the newly rendered HTML to the file served by GitHub Pages.

```bash
cp reports/bank_term_deposit_predictor.html docs/index.html
```

Commit and push the updated `docs/index.html` with your report changes.

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
