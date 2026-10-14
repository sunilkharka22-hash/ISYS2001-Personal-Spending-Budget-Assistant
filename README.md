# ISYS2001 Personal Spending & Budget Assistant

## Project Overview

This project is a Personal Spending & Budget Assistant developed for ISYS2001 Assessment 2.

The assistant helps users understand their spending by analysing financial data they provide and comparing their spending with a monthly budget.

The project combines Python, the Google Gemini API and Gradio to create a simple conversational finance assistant.

## Features

- Calculates total spending.
- Calculates spending by category.
- Compares spending with a monthly budget.
- Identifies the highest spending category.
- Provides a Budget Health analysis.
- Uses Google Gemini to answer finance-related questions.
- Uses the user's entered financial data when generating responses.
- Handles invalid and unexpected input.
- Provides a simple Gradio interface for non-programmers.

## How to Use

Enter spending data using the following format:

Food: 500
Transport: 300
Entertainment: 300
Groceries: 1000

Enter a monthly budget, for example:

3500

Then ask a question such as:

Where am I spending the most money?

The assistant analyses the provided data and generates a response.

## Example

### Input

Spending:

Food: 200
Transport: 100
Entertainment: 150
Groceries: 300

Budget:

3500

Question:

Where am I spending the most money?

### Example Output

The assistant identifies Groceries as the highest spending category at $300.

Total spending is $750, which represents approximately 21.4% of the $3,500 budget.

The budget health is classified as Healthy.

## Running the Project

The main project is provided as a Google Colab notebook:

`ISYS2001_Assessment_2_Finance_Assistant (1).ipynb`


Open the notebook in Google Colab and run the cells from top to bottom.

The project uses the Google Gemini API. The Gemini API key should be stored securely using Google Colab Secrets with the name:

`GEMINI_API_KEY`

The API key should not be written directly in the notebook or uploaded to GitHub.

## Personal Spending Data

The project uses estimated personal monthly spending data for demonstration and analysis. The spending values are estimates rather than bank transaction records.

## Technologies Used

- Python
- Google Gemini API
- Google Colab
- Gradio
- Lists and dictionaries
- Functions
- Conditional statements
- Loops
- Error handling
- Assertions/testing

## Repository Contents

- `ISYS2001_Assessment_2_Finance_Assistant (1).ipynb` – main project notebook.
- `Developer_Diary.md` – development diary documenting the development process and AI collaboration.
- `README.md` – project description and instructions.
