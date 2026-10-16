# ISYS2001 Personal Spending & Budget Assistant

## Project Overview

This project is my ISYS2001 Assessment 2 project.

I built a **Personal Spending & Budget Assistant** to help users understand their spending and see how it compares with their monthly budget.

The project uses Python for the financial calculations, Google Gemini for the conversational part of the assistant, and Gradio to provide a simple interface.

The main idea is that the assistant should use the spending data entered by the user when answering questions, rather than just giving general financial advice.

## What the Assistant Can Do

The finance assistant can:

- Calculate total spending.
- Show spending by category.
- Compare spending with a monthly budget.
- Find the category where the user spends the most.
- Analyse the user's budget health.
- Answer questions about the user's spending using Google Gemini.
- Use the financial data entered by the user when generating responses.
- Handle invalid or unexpected input.
- Provide a simple interface using Gradio.

## Example Input

The user can enter spending data in this format:

Food: 200
Transport: 100
Entertainment: 150
Groceries: 300

Monthly budget:

3500

Example question:

Where am I spending the most money?

## Example Output

For the example above, the assistant identifies **Groceries** as the highest spending category at **$300**.

The total spending is **$750**.

With a monthly budget of **$3,500**, the user has used approximately **21.4%** of their budget.

The Budget Health Analyzer classifies this as:

Budget Health: Healthy

The exact response from Gemini may vary because the conversational part of the project uses the Gemini API.

## How the Project Works

The project first reads the spending data entered by the user.

Python functions then calculate:

1. Total spending.
2. Spending by category.
3. The highest spending category.
4. The amount remaining from the budget.
5. The percentage of the budget that has been used.
6. The overall budget health.

The financial information is then provided to the Gemini assistant so it can answer the user's question using the actual data.

## Custom Budget Health Analyzer

I created my own **Budget Health Analyzer** as part of the project.

It calculates the percentage of the budget that has been used and gives the user one of three results:

- **Healthy** – less than 75% of the budget has been used.
- **Watch** – between 75% and 100% of the budget has been used.
- **Over Budget** – more than 100% of the budget has been used.

The function also checks for invalid values such as negative spending, zero budgets and non-numerical input.

## Testing

I tested the project with different types of data, including:

- Normal spending data.
- Different spending amounts.
- Spending at exactly 75% of the budget.
- Spending at exactly 100% of the budget.
- Spending over the budget.
- Invalid numerical input.
- Negative spending.
- Empty transaction data.
- Different questions for the Gemini assistant.

I also tested whether changing the financial data changed the assistant's response.

During testing, I found a problem where an empty transaction list could cause an error when the program tried to find the highest spending category. I fixed this by checking for empty transaction data before continuing with the calculations.

## Running the Project

The main project is provided as a Google Colab notebook.

Open the notebook in Google Colab and run the cells from top to bottom.

The project uses the Google Gemini API. The API key is stored securely using **Google Colab Secrets** with the following name:

GEMINI_API_KEY

The API key should not be written directly into the notebook or uploaded to GitHub.

## Personal Spending Data

The spending data used in the project is **estimated personal monthly spending data for demonstration purposes**. It is not connected to a bank account and does not represent actual bank transaction records.

## Technologies Used

- Python
- Google Gemini API
- Google Colab
- Gradio
- Lists and dictionaries
- Functions
- Loops
- Conditional statements
- `try/except` error handling
- Assertions and testing

## Repository Contents

- `ISYS2001_Assessment_2_Finance_Assistant (1).ipynb` – the main Google Colab notebook.
- `Developer_Diary.md` – development diary documenting the development process and use of AI.
- `README.md` – information about the project, features, example usage and how to run it.

## Project Purpose

The purpose of this project is to combine Python programming, financial calculations, a custom analytical tool, a real conversational AI model and a simple user interface into one practical finance assistant.
