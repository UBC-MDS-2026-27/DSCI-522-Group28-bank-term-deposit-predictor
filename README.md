# DSCI-522-Group28-bank-term-deposit-predictor

## Bank Term Deposit Predictor

## Authors: 
Du Du, Kshitij Agarwal, Indervir Dhillon, Rohit Bansal (Ordered by first name)

## Summary: 
This project asks whether a client will subscribe to a bank term deposit given the information available before a telephone marketing call is made. We use the Bank Marketing dataset from the UCI Machine Learning Repository, which records 45,211 clients who have been contacted by a Portuguese bank. 

## How to run the analysis

1. Install Git, uv 0.13.9, and Quarto 1.10.18. Check that `git`, `uv`, and `quarto` are available in your terminal.
2. Clone the repository and enter the project directory.

   ```bash
   git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group28-bank-term-deposit-predictor.git
   cd DSCI-522-Group28-bank-term-deposit-predictor
   ```

3. Install the locked Python dependencies.

   ```bash
   uv sync --locked
   ```

4. Render the Quarto report from the repository root. Rendering requires an internet connection to fetch the dataset.

   ```bash
   uv run quarto render reports/bank_term_deposit_predictor.qmd --to html
   ```

5. Open `reports/bank_term_deposit_predictor.html` in your browser. Rendering saves the raw dataset to `data/raw/bank_marketing.csv` and the training and test splits to `data/processed/`.

## Dependencies

- Python 3.14
- uv 0.13.9
- Quarto 1.10.18

Python packages, including Jupyter, pandas, and scikit-learn, are declared in `pyproject.toml` and pinned in `uv.lock`.

## Licenses

- **Code and software** are covered by the MIT License.
- **Report and documentation** are covered by the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International license (CC BY-NC-ND 4.0).

See [LICENSE.md](LICENSE.md) for the license terms.

## AI use statement:
We used ChatGPT 6.0, to help the project for uv, Quarto, and examples of Code of Conduct.
We used it in the Contributing.md, License.md to develop the structure and base text.
All AI-generated changes were reviewed, tested, and edited by our members, who take full responsibility for the content of the repository.

Example AI Prompt:
   - Provide me with some Code of Conduct example, for references to our project.
   - Find relevant articles or reports that have previously done similar to our project, and list the main purpose of them.

## Rendered report

[Predicting Bank Term Deposit Subscription (HTML)](https://ubc-mds-2026-27.github.io/DSCI-522-Group28-bank-term-deposit-predictor/reports/bank_term_deposit_predictor.html)
