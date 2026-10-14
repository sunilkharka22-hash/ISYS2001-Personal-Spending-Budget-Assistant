# Developer's Diary

## Development Note

The main development and integration work for this project was completed during the final development period before submission. The entries below are organised by the major stages of development rather than claiming that each stage occurred in a separate calendar week.

I used AI as a development partner throughout the project. I used AI to help me understand programming concepts, consider different implementation approaches, troubleshoot problems and improve testing. I reviewed and tested the suggestions rather than assuming that AI-generated responses were automatically correct.

Where the original wording of an AI prompt is not reproduced verbatim below, I have identified it as a reconstructed summary of the question I used during development rather than presenting it as an exact quotation.

---

## Stage 1 – Project Idea and Planning

### What I was trying to do

I started planning my ISYS2001 Assessment 2 finance assistant. I wanted to build a simple tool that could help a user understand their spending and compare it with a personal budget.

I decided to create a **Personal Spending & Budget Assistant**. The assistant would calculate total spending, analyse spending by category, compare spending with a personal budget and provide useful financial guidance.

Before writing the main Python code, I worked through the problem, identified the inputs and outputs, completed a worked example and created pseudocode.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

"Help me plan a finance assistant project for my ISYS2001 programming assessment. I need to understand the problem, identify inputs and outputs, work through an example, create pseudocode and then implement the solution in Python."

### AI response

The AI recommended breaking the project into smaller development stages, including understanding the problem, identifying inputs and outputs, working through a manual example, creating pseudocode and then implementing the Python solution.

### What I kept and why

I kept the step-by-step development approach because it helped me understand and design the solution before coding.

I also decided to use a personal spending and budget example because it gives the project a clear business and financial purpose.

### What I changed or rejected

I did not use the AI response as a complete finished solution. I used it as guidance and developed the project structure, example calculations and pseudocode for my own project.

This helped me understand what the program was supposed to do before writing the Python code.

---

## Stage 2 – Python Implementation and Testing

### What I was trying to do

I started implementing the main financial calculations in Python.

I wanted the program to:

- Calculate total spending.
- Calculate spending by category.
- Compare spending with the user's budget.
- Identify the highest spending category.
- Handle invalid input.

I used a list of dictionaries to represent the spending transactions and created separate functions for the different calculations.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

"How can I structure Python functions for a finance assistant that calculates total spending, spending by category, compares spending with a budget and finds the highest spending category?"

### AI response

The AI recommended separating the calculations into individual functions so that each function had a clear responsibility. It also suggested using a list of dictionaries to represent transaction data.

### What I kept and why

I kept the idea of using separate functions because it made the program easier to understand, test and debug.

I used a list of dictionaries for my spending data because each transaction could contain a category and an amount.

### What I changed or rejected

I adapted the approach to match my own project and financial data rather than copying a complete solution.

I also tested the functions with different spending amounts to make sure the calculations changed correctly when the data changed.

---

## Stage 3 – Gemini API and Finance Assistant Persona

### What I was trying to do

I wanted to connect my finance assistant to a real large language model so that users could ask questions about their spending in a conversational way.

I decided to use the Google Gemini API and created a finance-focused system instruction for the assistant.

The assistant was designed to use the user's provided financial data, avoid inventing financial information and stay focused on personal spending and budgeting.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

"How can I connect the Gemini API to my Python finance assistant and create a system instruction that keeps the assistant focused on the user's financial data and budgeting questions?"

### AI response

The AI recommended connecting the Gemini API to the Python program and using a system instruction to define the assistant's role, explain how it should use the user's financial data and specify how it should respond to unrelated questions.

### What I kept and why

I kept the finance-focused persona because it makes the assistant more useful and relevant to the project.

I also kept the instruction that the assistant should use the user's provided financial data and should not invent financial information.

### What I changed or rejected

I changed the wording of the system instruction to match my own project and data.

I also stored the Gemini API key using Google Colab Secrets rather than placing the key directly in the notebook.

I tested the Gemini connection by asking questions about my spending and confirmed that the responses used my provided financial data.

---

## Stage 4 – Custom Budget Health Analyzer

### What I was trying to do

I wanted to add my own analytical tool so the finance assistant could provide more than just basic spending calculations.

I decided to create a **Budget Health Analyzer**.

The tool calculates the percentage of the budget used and classifies the result as:

- Healthy
- Watch
- Over Budget

The tool also handles invalid inputs.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

"Help me design a custom budget health analysis function that calculates the percentage of a budget used, classifies the result and handles invalid input without crashing."

### AI response

The AI suggested calculating the percentage of the budget used and using conditional statements to classify the result. It also suggested using `try/except` to handle invalid numerical input.

### What I kept and why

I kept the percentage-based budget health approach because it provides a simple and useful financial result.

I also kept input validation because the assessment requires the custom tool to handle bad input without crashing.

### What I changed or rejected

I adapted the thresholds and messages to my own finance assistant rather than using an AI suggestion as a complete solution.

I tested the tool using:

- Normal financial values.
- Non-numeric values.
- Negative spending.
- A zero budget.

The tool returned clear error messages for invalid inputs.

---

## Stage 5 – Debugging and Gradio Interface

### What I was trying to do

I focused on testing the finance assistant with different types of input and creating a simple interface that a non-programmer could use.

I used Gradio to create an interface where a user could enter spending data, enter a monthly budget and ask a question about their finances.

I also wanted to identify and fix at least one problem during development.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

"How can I test my finance assistant with normal and invalid inputs, handle errors and connect the Python finance assistant to a simple Gradio interface?"

### AI response

The AI recommended testing normal, invalid and unexpected inputs and using Gradio to create a simple interface for users to enter their spending information and ask questions.

### What I kept and why

I kept the Gradio interface because it provides a simple way for a user to interact with the finance assistant without needing to understand the Python code.

I also kept input validation and error handling to prevent the program from crashing.

### What I changed or rejected

During testing, I found that an empty transaction list caused a problem when the program tried to identify the highest spending category.

I changed the program to check whether transaction data was available before performing the calculations.

After making the change, the empty transaction test produced a clear message instead of causing an error.

I also added handling for temporary Gemini availability errors so that the interface can return a helpful message if the Gemini service is temporarily unavailable.

---

## Stage 6 – Final Testing and Reflection

### What I was trying to do

I completed the main features of the Personal Spending & Budget Assistant and focused on final testing.

I tested the program using:

- Normal spending data.
- Different financial data.
- An exact-budget situation.
- An over-budget situation.
- Invalid inputs.
- Empty transaction data.
- Different questions through the Gemini assistant.
- The Gradio interface.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

"What additional tests should I perform on my finance assistant to check normal, invalid, empty and different financial data, and how can I confirm that the assistant is actually using the user's financial data?"

### AI response

The AI recommended testing different budget situations, invalid input, empty data and unclear questions. It also recommended checking that the assistant's responses changed when the financial data changed.

### What I kept and why

I kept these tests because they cover both normal and unexpected situations.

I also kept the test showing that the Gemini assistant uses the provided financial data because this demonstrates that the assistant is not simply giving generic financial responses.

For example, when I changed the spending data, the assistant recalculated the total spending, percentage of budget used and highest spending category.

### What I changed or rejected

During testing, I found and fixed the empty transaction problem.

I also added input validation and temporary Gemini error handling.

I rejected the idea of relying only on generic example data because the purpose of my project is to analyse the spending data provided to the assistant.

### Final Reflection

The development process helped me understand how Python functions, conditional statements, dictionaries, error handling, APIs and Gradio can work together to create a practical application.

I also learned that testing is important because some problems only became visible when I used unexpected or invalid inputs.

Using AI was useful for brainstorming, troubleshooting and understanding different implementation approaches. However, I still needed to test the suggestions myself and change them when they did not work correctly for my project.

The final project combines Python-based financial calculations, a custom budget analysis tool, a Gemini conversational assistant and a Gradio interface.
