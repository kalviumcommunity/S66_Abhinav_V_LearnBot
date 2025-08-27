# 📚 LearnBot

LearnBot is a simple **AI-powered Study Helper** that makes studying easier.  
You can paste your notes, articles, or paragraphs, and LearnBot will explain them in **simple words**—like how a teacher explains to a 10th-class student.  

---

## 🚀 Features
- Paste any text and get a **simplified explanation**  
- **One-click button** to generate answers  
- Clean and **easy-to-use UI**  
- Powered by **Generative AI** (OpenAI API)  

---

## 🛠️ Tech Stack
- **Frontend:** React + Tailwind CSS  
- **Backend (optional):** Node.js + Express  
- **AI API:** OpenAI  

---

## 📝 System and User Prompts

To implement **LearnBot**, we define clear prompts for the AI to ensure consistent and simple explanations.  
These prompts are designed using the **RTFC Framework**.


### 🔹 System Prompt
You are LearnBot, an AI Study Helper.  
Your role is to act like a teacher who explains complex study material in **simple and easy-to-understand language**.  
Always keep answers short, clear, and suitable for a **students**.


### 🔹 User Prompt
Simplify the following text so that a students can easily understand it:

[USER_INPUT_TEXT]


### 📌 RTFC Framework Usage
- **R (Role):** Defined in the system prompt as a friendly teacher/study helper.  
- **T (Task):** Simplify notes, articles, or paragraphs into simple explanations.  
- **F (Format):** Provide answers in short, clear sentences (easy-to-read).  
- **C (Constraints):** Avoid technical jargon; keep the explanation school-level.

---

## 🎯 Zero-Shot Prompting  

In **LearnBot**, we apply **Zero-Shot Prompting**, where the AI is asked to perform the task without being given any prior examples.  
Instead of showing sample inputs/outputs, the AI directly relies on the instructions to understand the task.  
This makes the system **flexible and adaptable** for different kinds of study material.  


### 🔹 Zero-Shot Prompt  

Simplify the following academic text into a clear, short, and easy-to-read explanation:
        Photosynthesis is a process by which plants convert light energy into chemical energy that can later be released to fuel the organisms' activities.


### 📌 Why Zero-Shot Prompting?

- The AI is not given any examples — only task-specific instructions.  
- It can generalize across **different subjects and topics**.  
- Ensures **scalable and flexible explanations** without needing predefined cases.  

---


## 🎯 One-Shot Prompting  

In **LearnBot**, we use **One-Shot Prompting**, where the AI is given a **single example** before performing the task.  
This helps guide the model with a reference while still keeping it generalizable.  


### 🔹 One-Shot Prompt  

**Prompt (with one example):**  

Example Input:  

    The mitochondria is known as the powerhouse of the cell because it generates energy in the form of ATP through cellular respiration.

Example Expected Output:  

    Mitochondria are parts of the cell that produce energy. That’s why they are called the powerhouse of the cell.

Now simplify the following text:  

    Photosynthesis is a process by which plants convert light energy into chemical energy that can later be released to fuel the organisms' activities.

### 📌 Why One-Shot Prompting?

- Provides **one guiding example** to set the response pattern.  
- Ensures the AI generates **consistent, simplified outputs**.  
- Reduces ambiguity compared to zero-shot prompting.  

---

## 🎯 Multi-Shot Prompting  

In **LearnBot**, we apply **Multi-Shot Prompting**, where the AI is provided with **multiple examples** before being asked to solve the real task.  
This method ensures the AI clearly understands the **pattern, style, and expectations** of the simplified output.  


### 🔹 Multi-Shot Prompt  

**Prompt (with multiple examples):**  

Example 1:  
Input:  
        The mitochondria is known as the powerhouse of the cell because it generates energy in the form of ATP through cellular respiration.

Expected Output:  
        Mitochondria are parts of the cell that make energy. That’s why they are called the powerhouse of the cell.


Example 2:  
Input:  
        Water evaporates from the surface of oceans, lakes, and rivers, then condenses into clouds, and finally falls back as rain, completing the water cycle.

Expected Output:  
        Water turns into vapor, forms clouds, and falls back as rain. This is called the water cycle.

Now simplify the following text:  

Photosynthesis is a process by which plants convert light energy into chemical energy that can later be released to fuel the organisms' activities.


### 📌 Why Multi-Shot Prompting?

- Gives the AI **multiple reference examples** to guide the response.  
- Helps in **complex explanations** where one example is not enough.  
- Reduces errors and improves the **accuracy and consistency** of simplified outputs.  

---

## 🎯 Dynamic Prompting  

In **LearnBot**, we use **Dynamic Prompting**, where the prompt is automatically adapted based on the **user’s input context** (e.g., subject, topic, or difficulty level).  
This makes the system **flexible and personalized**, instead of relying on fixed instructions.  

### 🔹 Dynamic Prompt Example  

**Prompt Template:**  
Simplify the following text related to **{{subject}}**.  
Make the explanation **{{difficulty_level}}** and easy to understand.  

**User Input (Generated Dynamically):**  
Subject: Biology  

Difficulty Level: Easy  

Text:  
Photosynthesis is a process by which plants convert light energy into chemical energy that can later be released to fuel the organisms' activities.


### Example Execution  

If the user provides the above input, the dynamically generated prompt becomes:  

Text:-
    Simplify the following text related to Biology.  
    Make the explanation Easy and easy to understand.  

Text: 
        Photosynthesis is a process by which plants convert light energy into chemical energy that can later be released to fuel the organisms' activities.

Expected Output:
        Photosynthesis is how plants use sunlight to make food and store energy.

### 📌 Why Dynamic Prompting?

- Automatically adapts prompts to different subjects and difficulty levels.
- Makes the system more personalized for students.
- Reduces manual re-writing of prompts while ensuring consistent simplified explanations.

---

## 🎯 Chain-of-Thought Prompting

In **LearnBot**, we use **Chain-of-Thought (CoT) prompting** to nudge the AI to **think through the passage internally** (step by step) and then show **only the final, simplified answer**.  
This gives clearer explanations without exposing the hidden reasoning.

### 🔹 Chain-of-Thought Prompt

**System Prompt (Deliberate style):**  
You are LearnBot, an AI study helper. First, **reason through the passage internally** to identify the main idea, key steps, cause–effect, and important terms. **Do not reveal your reasoning.**  
Then return **only** the final answer in this exact format and nothing else:

- **Title:** <short topic name>  
- **Summary:** <2–4 plain sentences>  
- **Key Points:** <3–5 concise bullets>  
- **Glossary:** <1–2 short term definitions, if needed>  

Constraints: Keep under 120 words, avoid jargon, keep sentences short, and be factually accurate.

**User Prompt:**  
Simplify the following text and follow the required output format:  
Photosynthesis is a process by which plants convert light energy into chemical energy that can later be released to fuel the organisms' activities.


### 🔹 Example Final Output (shown to user)

- **Title:** Photosynthesis  
- **Summary:** Plants use light to make chemical energy they can store and use later. This process turns light into food energy inside leaves.  
- **Key Points:**  
  - Light energy is captured by chlorophyll.  
  - Energy is stored in chemical compounds.  
  - The stored energy powers plant activities.  
- **Glossary:**  
  - **Chlorophyll:** Green pigment that absorbs light.


### 📌 How we used Chain-of-Thought Prompting
- We instruct the model to **think step by step internally**, improving accuracy and structure.  
- We **hide the reasoning** and **only output a clean, formatted answer**, keeping results concise and consistent. 

---

## 🧪 Evaluation Dataset & Testing Framework  

To measure if **LearnBot** is performing correctly, we built a structured **evaluation pipeline**.  
It includes:  
- ✅ A dataset of at least **5 study Q&A samples**  
- ✅ A **judge prompt** with clear evaluation parameters  
- ✅ A simple **testing framework** to run all cases automatically  


### 📂 Evaluation Dataset (5 Samples)  
```json
[
  {
    "id": 1,
    "question": "What is photosynthesis?",
    "expected": "Photosynthesis is the process by which plants make food using sunlight, water, and carbon dioxide, producing oxygen as a byproduct."
  },
  {
    "id": 2,
    "question": "Explain Newton's first law of motion.",
    "expected": "An object at rest stays at rest and an object in motion stays in motion at the same speed and direction unless acted upon by an external force."
  },
  {
    "id": 3,
    "question": "Differentiate between mitosis and meiosis.",
    "expected": "Mitosis produces two identical cells for growth/repair, while meiosis produces four genetically different gametes for reproduction."
  },
  {
    "id": 4,
    "question": "What is the capital of France?",
    "expected": "Paris."
  },
  {
    "id": 5,
    "question": "Solve: 12 ÷ 3 × 2",
    "expected": "8"
  }
]
```
### 🧑‍⚖️ Judge Prompt
You are a strict evaluator. Compare the AI's answer with the expected result.

Evaluation Parameters:  
1. Correctness – Did the AI give the right answer?  
2. Completeness – Is the answer fully addressing the question?  
3. Clarity – Is the explanation simple and easy to understand?  
4. Conciseness – Is it short and to the point (no unnecessary info)?  

Return only: Pass / Fail with a one-sentence justification.

### ⚙️ Testing Framework
We used a Python test runner to automate evaluation:

for test in dataset:
    ai_output = run_model(test["question"])          
    verdict = judge(ai_output, test["expected"])   
    print(f"Test {test['id']}: {verdict}")

### ✅ Why This Setup?

- Objectivity: The judge uses fixed rules (correctness, completeness, format, clarity).
- Automation: All 5+ samples are tested in one go.
- Reproducibility: New models can be tested with the same dataset.
- Reliability: Gives clear ✅ Pass / ❌ Fail results for improvement tracking.

---

## 🔡 Tokens & Tokenization (LearnBot)  

To make **LearnBot** efficient, we also **track tokens** after every AI call.  


### 📝 What are Tokens?  
- A **token** is like a small piece of text (a word, part of a word, or punctuation).  
- Example: `"Learning is fun!"` → might be split into tokens like:  
    ["Learning", " is", " fun", "!"]

- The AI processes **tokens, not whole sentences**.  
- Fewer tokens = faster response + lower cost.  


### ⚙️ Implementation in LearnBot  
After each AI request, we **log the number of tokens used** in the console/terminal.  

```python
response = run_model(user_input)
print("AI Response:", response["text"])
print("🔢 Tokens used:", response["usage"]["total_tokens"])
```
### ✅ Why This Helps?
Efficiency → Track how much text LearnBot is processing.

Cost Control → Token usage directly affects API cost.

Debugging → Helps optimize prompts and avoid unnecessary long responses.

### 📊 Sample Log Output
User Input: What is photosynthesis?
AI Response: Photosynthesis is the process by which plants make food using sunlight.
🔢 Tokens used: 24


---