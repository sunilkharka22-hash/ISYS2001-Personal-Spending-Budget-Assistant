# Developer's Diary

## Week 1 – Project Idea and Planning

### What I was trying to do
I started planning my Assessment 2 finance assistant. I wanted to build a simple tool that could help a user understand their spending and compare it with a personal budget.

I decided to create a **Personal Spending & Budget Assistant**. The assistant would calculate total spending, analyse spending by category, compare spending with a budget and provide useful financial guidance.

### AI prompt/question
I asked ChatGPT for help understanding how I could structure a finance assistant project and what components would be useful for the assessment.

### AI response
The AI suggested breaking the project into smaller stages, including defining the problem, identifying inputs and outputs, working through an example manually, creating pseudocode and then implementing the solution in Python.

### What I kept and why
I kept the step-by-step development approach because it matched the assessment requirement to understand and design the solution before coding.

I also decided to use a personal spending and budget example because it gives the project a clear business and financial purpose.

### What I changed or rejected
I did not use the AI response as a complete finished solution. I used it as guidance and developed the project structure and calculations myself.

---

## Week 2 – Python Implementation and Testing

### What I was trying to do
I started implementing the main financial calculations in Python. I wanted the program to calculate total spending, spending by category, budget comparison and the highest spending category.

### AI prompt/question
I asked ChatGPT for guidance on how to structure the Python functions for calculating and analysing spending data.

### AI response
The AI suggested separating the calculations into individual functions so that each function would have one clear responsibility. It also suggested using lists of dictionaries to represent transaction data.

### What I kept and why
I kept the idea of using separate functions because it made the program easier to understand, test and debug.

I used a list of dictionaries for my spending data because each transaction could contain a category and an amount.

### What I changed or rejected
I adapted the suggested approach to match my own project and financial data rather than copying a complete solution.

I also tested the functions with different spending amounts to make sure the calculations changed correctly when the data changed.

---

## Week 3 – Gemini API and Finance Assistant Persona

### What I was trying to do
I started connecting my finance assistant to a real large language model so that users could ask questions about their spending in a conversational way.

I decided to use the Google Gemini API and created a finance-focused system instruction for the assistant.

### AI prompt/question
I asked ChatGPT for guidance on connecting Gemini to my Python program and creating a suitable finance assistant persona.

### AI response
The AI suggested using the Gemini API with a system instruction that defines the assistant's role, explains how it should use the user's financial data and tells it how to respond to unrelated questions.

### What I kept and why
I kept the finance-focused persona because it makes the assistant more useful and relevant to the project.

I also kept the instruction that the assistant should use the user's provided financial data and should not invent financial information.

### What I changed or rejected
I changed the wording of the system instruction to match my own project and data.

I also made sure that my Gemini API key was stored securely in Google Colab Secrets rather than directly in the notebook.

I tested the connection by asking the assistant questions about my spending and confirmed that the responses used my provided financial data.

---

## Week 4 – Custom Budget Health Analyzer

### What I was trying to do
I wanted to add my own analytical tool so the finance assistant could provide more than just basic spending calculations.

I decided to create a **Budget Health Analyzer** that calculates the percentage of the budget used and classifies the budget as Healthy, Watch or Over Budget.

### AI prompt/question
I asked ChatGPT for guidance on designing a custom financial analysis function that could handle different budget situations and invalid input.

### AI response
The AI suggested calculating the percentage of the budget used and using conditional statements to classify the result. It also suggested using try/except to handle invalid numerical input.

### What I kept and why
I kept the percentage-based budget health approach because it provides a simple and useful financial result.

I also kept the input validation because the assessment requires the custom tool to handle bad input without crashing.

### What I changed or rejected
I adapted the thresholds and messages to my own finance assistant rather than using the AI suggestion as a complete solution.

I tested the tool using normal values as well as non-numeric values, negative spending and a zero budget. The tool returned clear error messages for invalid inputs.

---

## Week 5 – Debugging and Gradio Interface

### What I was trying to do
I focused on testing the finance assistant with different types of input and creating a simple interface that a non-programmer could use.

I also wanted to identify and fix at least one problem during development.

### AI prompt/question
I asked ChatGPT for help with testing the program, handling invalid input and connecting the finance assistant to a simple Gradio interface.

### AI response
The AI suggested testing normal, invalid and unexpected inputs. It also suggested using Gradio to create a simple text-based interface for asking questions.

### What I kept and why
I kept the Gradio interface because it provides a simple way for a user to interact with the finance assistant without needing to understand the Python code.

I also kept input validation and error handling to prevent the program from crashing.

### What I changed or rejected
During testing, I found that an empty transaction list caused a problem when the program tried to identify the highest spending category.

I changed the program to check whether transaction data was available before performing the calculations. After the change, the empty transaction test produced a clear message instead of causing an error.

I also added handling for temporary Gemini availability errors so that the interface can return a helpful message if the Gemini service is temporarily unavailable.

---

## Week 6 – Final Testing and Reflection

### What I was trying to do
I completed the main features of the Personal Spending & Budget Assistant and focused on final testing.

I tested the program using normal spending data, different financial data, an exact budget, an over-budget situation and invalid inputs.

I also tested the Gemini-powered assistant and the Gradio interface.

### AI prompt/question
I asked ChatGPT for help reviewing my testing approach and identifying additional cases that could be tested to make the finance assistant more reliable.

### AI response
The AI suggested testing different budget situations, invalid input, empty data and unclear user questions. It also suggested checking that the assistant's responses changed when the financial data changed.

### What I kept and why
I kept these tests because they cover both normal and unexpected situations.

I also kept the test showing that the Gemini assistant uses my provided financial data because this demonstrates that the assistant is not simply giving generic financial responses.

### What I changed or rejected
During testing, I found and fixed the empty transaction problem. I also added input validation and temporary Gemini error handling.

I rejected the idea of relying only on generic example data because the purpose of my project is to analyse my provided personal spending estimates.

### Final Reflection
The development process helped me understand how Python functions, conditional statements, dictionaries, error handling, APIs and Gradio can work together to create a practical application.

I also learned that testing is important because some problems only became visible when I used unexpected or invalid inputs.
