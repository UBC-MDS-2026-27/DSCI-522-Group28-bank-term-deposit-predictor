# Bank Term Deposit Predictor

## Authors: 
Du Du, Kshitij Agarwal, Indervir Dhillon, Rohit Bansal

## Summary: 
This project asks whether a client will subscribe to a bank term deposit given the information available before a telephone marketing call is made. We use the Bank Marketing dataset from the UCI Machine Learning Repository, which records 45,211 clients who have been contacted by a Portuguese bank. 

## How to run the analysis

Install Git and Docker Desktop, then start Docker Desktop. Clone the repository and enter the project directory:
On Windows, run these commands in Git Bash (included with Git for Windows) so `ssh-keygen` and `~` paths work as written.

```bash
git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group28-bank-term-deposit-predictor.git
cd DSCI-522-Group28-bank-term-deposit-predictor
```

### 1. Set up your SSH key

If you don't already have an SSH key at `~/.ssh/id_ed25519.pub`, run the following command and press Enter to accept the default location:

```bash
ssh-keygen -t ed25519
```

### 2. Download the Docker image

From the project directory, run:

```bash
docker compose pull
```

### 3. Render the report

From the same directory, run the analysis and render the report.

```bash
docker compose run --rm analysis-env uv run quarto render
```

Rendering needs an internet connection to download the Bank Marketing dataset from the UCI Machine Learning Repository. It saves the raw data to `data/raw/bank_marketing.csv` and the training and test splits to `data/processed/`.

Open `reports/bank_term_deposit_predictor.html` in your browser to view the report. The `--rm` option removes the container automatically when the command finishes.

If you want to make changes to the project, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Dependencies

Docker runs the analysis in an image built from the [Dockerfile](Dockerfile). The image includes Python, uv, and Quarto. The Python packages are declared in [pyproject.toml](pyproject.toml) and pinned in [uv.lock](uv.lock).


## Licenses

Code and software are covered by the MIT License, while the report and documentation are covered by the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International license (CC BY-NC-ND 4.0). See [LICENSE.md](LICENSE.md) for the full license terms and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for our community standards.


## AI use statement:
We used ChatGPT 6.0 to assist with uv, Quarto, and examples for `CODE_OF_CONDUCT.md`, as well as to draft the structure and base text of `CONTRIBUTING.md` and `LICENSE.md`. For example, we asked it for Code of Conduct examples and for summaries of similar prior projects. All AI-generated changes were reviewed, tested, and edited by our members, who take full responsibility for the content of the repository.

Example AI Prompt:
   - Provide me with some Code of Conduct example, for references to our project.
   - Find relevant articles or reports that have previously done similar to our project, and list the main purpose of them.
   - Verify if our repository meets all Milestone 2 requirements and check `README.md` and `CONTRIBUTING.md` for typos or formatting issues.

## Rendered report

[Predicting Bank Term Deposit Subscription (HTML)](https://ubc-mds-2026-27.github.io/DSCI-522-Group28-bank-term-deposit-predictor/)