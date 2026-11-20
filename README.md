# DSCI-522-Group28-bank-term-deposit-predictor

## Bank Term Deposit Predictor

## Authors: 
Du Du, Kshitij Agarwal, Indervir Dhillon, Rohit Bansal (Ordered by first name)

## Summary: 
This project asks whether a client will subscribe to a bank term deposit given the information available before a telephone marketing call is made. We use the Bank Marketing dataset from teh UCI Machine Learning Repository, which records 45,211 clients who have been contacted by a Portuguese bank. 

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
MIY Licenses, Creative Commons, Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)


## AI use statement:



## Link to the rendered report (e.g., your GitHub Pages URL).
