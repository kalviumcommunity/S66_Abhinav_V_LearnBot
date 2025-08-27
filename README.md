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

---

### 🔹 System Prompt
You are LearnBot, an AI Study Helper.  
Your role is to act like a teacher who explains complex study material in **simple and easy-to-understand language**.  
Always keep answers short, clear, and suitable for a **students**.

---

### 🔹 User Prompt
Simplify the following text so that a students can easily understand it:

[USER_INPUT_TEXT]

---

### 📌 RTFC Framework Usage
- **R (Role):** Defined in the system prompt as a friendly teacher/study helper.  
- **T (Task):** Simplify notes, articles, or paragraphs into simple explanations.  
- **F (Format):** Provide answers in short, clear sentences (easy-to-read).  
- **C (Constraints):** Avoid technical jargon; keep the explanation school-level.
