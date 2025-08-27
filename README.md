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