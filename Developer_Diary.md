# Developer's Diary

## Development Note

Most of the development and integration work for this project was completed during the final development period before submission. I have organised this diary around the main stages of my project rather than pretending that every stage happened in a separate week.

I used AI as a development partner while working on the project. I mainly used it to understand programming concepts, get ideas for how to structure parts of the program, troubleshoot errors and think about testing. I did not assume that everything AI suggested was correct. I tested the suggestions myself and changed things when they did not work or did not fit my project.

Where I have not included the exact original wording of an AI prompt, I have clearly labelled it as a reconstructed version of the question I used during development.

---

## Stage 1 – Project Idea and Planning

### What I was trying to do

I started by thinking about what kind of finance assistant I could build for my ISYS2001 Assessment 2. I wanted to make something simple but useful that could help a person understand where their money was going and whether they were staying within their budget.

I decided to build a **Personal Spending & Budget Assistant**. The idea was for the assistant to calculate total spending, break spending down by category, compare it with a budget and give some useful guidance based on the data.

Before starting the main Python code, I worked through the problem first. I identified the inputs and outputs, did a worked example by hand and then wrote pseudocode.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

> "Help me plan a finance assistant project for my ISYS2001 programming assessment. I need to understand the problem, identify inputs and outputs, work through an example, create pseudocode and then implement the solution in Python."

### AI response

The AI suggested breaking the project into smaller steps. These included understanding the problem, identifying inputs and outputs, doing a manual example, writing pseudocode and then moving into the Python implementation.

### What I kept and why

I kept this step-by-step approach because it made the project easier for me to understand before I started coding.

I also liked the idea of using spending and budgeting because it gave my project a clear purpose instead of just making a program that performed calculations without a real use.

### What I changed or rejected

I did not take the AI response and use it as a complete finished solution. I used it mainly as guidance and then worked out the project structure, calculations and pseudocode for my own finance assistant.

Doing this first also helped me understand what I wanted the program to do before I started writing the actual Python code.

---

## Stage 2 – Python Implementation and Testing

### What I was trying to do

Once I had planned the project, I started building the main financial calculations in Python.

I wanted the program to:

- Calculate total spending.
- Calculate spending by category.
- Compare spending with the user's budget.
- Find the highest spending category.
- Handle invalid input.

I decided to use a list of dictionaries for the transactions and separate functions for the different calculations.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

> "How can I structure Python functions for a finance assistant that calculates total spending, spending by category, compares spending with a budget and finds the highest spending category?"

### AI response

The AI suggested using separate functions so that each function had one main job. It also suggested using a list of dictionaries to store the transaction category and amount.

### What I kept and why

I kept the separate functions because I found that they made the code easier to read and test. If something went wrong with one calculation, I could look at that particular function instead of having everything in one large block of code.

I also used a list of dictionaries because it made sense for my transaction data. Each transaction could have a category and an amount.

### What I changed or rejected

I changed the approach to fit my own project and the spending data I was using instead of simply copying a complete solution from AI.

I also tested the functions with different amounts to check that the results actually changed when the financial data changed.

---

## Stage 3 – Gemini API and Finance Assistant Persona

### What I was trying to do

After getting the basic calculations working, I wanted the project to become more conversational. I wanted a user to be able to ask questions about their spending rather than only seeing calculated numbers.

I decided to use the Google Gemini API and created a finance-focused system instruction for the assistant.

I wanted the assistant to use the financial information provided by the user, avoid making up financial information and stay focused on spending and budgeting questions.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

> "How can I connect the Gemini API to my Python finance assistant and create a system instruction that keeps the assistant focused on the user's financial data and budgeting questions?"

### AI response

The AI suggested connecting Gemini to the Python program and using a system instruction to explain the assistant's role and how it should use the financial information provided by the user. It also suggested handling questions that were unrelated to the purpose of the assistant.

### What I kept and why

I kept the finance-focused persona because I did not want the project to feel like a general chatbot. I wanted it to behave like a finance assistant that focuses on spending and budgeting.

I also kept the instruction that the assistant should use the user's financial data and should not invent information that was not provided.

### What I changed or rejected

I changed the wording of the system instruction so that it matched my own project and the way I wanted the assistant to respond.

I also stored my Gemini API key using Google Colab Secrets instead of putting the actual key directly into the notebook. This was important because I did not want the API key to be visible in my code or uploaded to GitHub.

I tested the Gemini connection by asking questions about my spending and checked whether the response actually used the financial data I provided.

---

## Stage 4 – Custom Budget Health Analyzer

### What I was trying to do

I wanted to add something of my own to the project rather than only making basic calculations and connecting an API.

I decided to create a **Budget Health Analyzer**. This tool calculates how much of the user's budget has been used and then gives the budget a simple status:

- Healthy
- Watch
- Over Budget

I also wanted the tool to handle incorrect input instead of crashing.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

> "Help me design a custom budget health analysis function that calculates the percentage of a budget used, classifies the result and handles invalid input without crashing."

### AI response

The AI suggested calculating the percentage of the budget that had been used and then using conditional statements to decide whether the result was Healthy, Watch or Over Budget. It also suggested using `try/except` to deal with invalid numerical input.

### What I kept and why

I kept the percentage-based approach because I thought it gave the user a simple result that was easy to understand.

I also kept the input validation because I wanted the custom tool to handle bad input properly instead of stopping the whole program.

### What I changed or rejected

I changed the thresholds and messages so they suited my own finance assistant. I did not just copy the suggested function as a finished solution.

I tested the tool with:

- Normal financial values.
- Non-numeric values.
- Negative spending.
- A zero budget.

The invalid inputs produced clear error messages instead of causing the program to crash.

---

## Stage 5 – Debugging and Gradio Interface

### What I was trying to do

At this stage, I focused more on testing the program with different types of input and making the project easier for someone else to use.

I used Gradio to create a simple interface where a user can enter their spending data, enter a monthly budget and ask a question about their finances.

I also needed to find and fix at least one problem during development.

### AI prompt/question

**Prompt/question used (reconstructed from my development work):**

> "How can I test my finance assistant with normal and invalid inputs, handle errors and connect the Python finance assistant to a simple Gradio interface?"

### AI response

The AI suggested testing normal and invalid inputs and using Gradio to make a simple interface where users could enter their spending information and ask questions.

### What I kept and why

I kept the Gradio interface because it makes the project much easier for someone to use. A person does not need to understand the Python code to enter their spending and ask a question.

I also kept the input validation and error handling because I wanted the program to respond properly when something went wrong.

### What I changed or rejected

While testing, I found a problem when there were no transactions. The program was trying to find the highest spending category even though there was no transaction data available.

I fixed this by checking whether there was transaction data before continuing with the calculations.

After changing it, I tested the empty transaction case again and the program displayed a clear message instead of producing an error.

I also added handling for temporary Gemini availability problems. This means that if the Gemini service is temporarily unavailable, the interface can give the user a helpful message rather than simply crashing.

---

## Stage 6 – Final Testing and Reflection

### What I was trying to do

Once the main features were working, I focused on testing the whole finance assistant.

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

> "What additional tests should I perform on my finance assistant to check normal, invalid, empty and different financial data, and how can I confirm that the assistant is actually using the user's financial data?"

### AI response

The AI suggested testing different budget situations, invalid input, empty data and unclear questions. It also suggested checking whether the assistant's response changed when the financial data changed.

### What I kept and why

I kept these tests because they gave me a better idea of how the program behaved in both normal and unexpected situations.

One test I thought was particularly important was changing the financial data and checking whether the assistant's answer changed as well. This helped me check that Gemini was actually being given the user's financial information rather than just producing a generic finance answer.

For example, when I changed the spending data, the assistant recalculated the total spending, budget percentage and highest spending category.

### What I changed or rejected

During testing, I found and fixed the empty transaction problem.

I also added input validation and handling for temporary Gemini errors.

I rejected the idea of relying only on generic example data because the main purpose of my project is to analyse the spending data entered by the user.

### Final Reflection

Working on this project helped me understand how different parts of Python can be combined to make a practical application. I used functions, conditional statements, dictionaries, error handling, API requests and Gradio as part of the project.

One thing I learned is that testing is really important. Some problems were not obvious when I first wrote the code and only appeared when I tried invalid or unexpected inputs.

AI was useful throughout the project, especially when I was stuck, trying to understand an error or thinking about different ways to implement something. However, I learned that I could not just assume the AI's answer was correct. I had to run the code, check the results and change things when they did not work properly.

The final project combines my Python financial calculations, my custom Budget Health Analyzer, the Gemini conversational assistant and the Gradio interface into one finance assistant.
