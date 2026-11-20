# DSCI-522-Group28-bank-term-deposit-predictor

## Bank Term Deposit Predictor

## Authors: 
Du Du, Kshitij Agarwal, Indervir Dhillon, Rohit Bansal (Ordered by first name)

## Summary: 
This project asks whether a client will subscribe to a bank term deposit given the information available before a telephone marketing call is made. We use the Bank Marketing dataset from teh UCI Machine Learning Repository, which records 45,211 clients who have been contacted by a Portuguese bank. You can access our analysis from this link: https://ubc-mds-2026-27.github.io/DSCI-522-Group28-bank-term-deposit-predictor/reports/bank_term_deposit_predictor.html

## How to run the analysis: 
The first time you access the project:
1. Install Git, uv, and Quarto. Make sure that the git, uv, and quarto commands are available in your terminal.

2. Clone the repository and enter
git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group28-bank-term-deposit-predictor.git
cd DSCI-522-Group28-bank-term-deposit-predictor

3. Install Python version and packages
uv sync --locked

4. Render the Quarto report from the repository root
uv run quarto render reports/bank_term_deposit_predictor.qmd --to html

5. Open reports/bank_term_deposit_predictor.html in your browswer. The render writes the fetched dataset to data/raw/bank_marketing.csv and the training and test sets splits to data/processed/.


## Dependencies: 
Python 3.14
uv
Quarto
Python dependencies including Jupyter, pandas, scikit-learn are in pyproject.toml


## Licenses: 
MIT License, Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)


## AI use statement:
We used ChatGPT 6.0, to help the project for uv, Quarto, and examples of Code of Conduct.
We used it in the Contributing.md, License.md to develop the structure and base text.
All AI-generated changes were reviewed, tested, and edited by our members, who take fully responsibility for the content of the repository.


## Link to the rendered report (e.g., your GitHub Pages URL).
file:///Users/nexodu/Downloads/DSCI-522-Group28-bank-term-deposit-predictor-main/reports/bank_term_deposit_predictor.html
