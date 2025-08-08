# ATM-Simulation-project-two-version-
# 🏧 ATM Simulation Project (Two Versions)

Welcome to the *ATM Simulation Project*, a beginner-friendly Python project that simulates the core functions of an ATM. This project was developed in two versions to illustrate the evolution from basic scripting to more structured and modular programming using functions.

---

## 🧠 Purpose of the Project

The goal of this project is to simulate real-life ATM operations through the command line, helping beginners strengthen their understanding of:

- Conditional statements  
- Loops  
- Functions  
- Exception handling  
- File operations  
- Modular programming

This project can be a great stepping stone for those aiming to build more advanced banking or finance-related software in the future.

---

## 🧱 Why Two Versions?

To show the development of a beginner’s coding journey and learning curve, this ATM simulation is provided in *two different versions*:

### 🔹 Version 1 – Basic Version (No Functions)

This version is written *without using functions*, where all logic is placed in a single script. It focuses on helping beginners:

- Practice control flow (if, while, break, continue)
- Understand how to process user input
- Handle incorrect input with try-except
- Simulate basic ATM features like:
  - Password validation
  - Balance inquiry
  - Deposit
  - Withdrawal
  - Card return

> 🧩 *Limitation:* The code can get repetitive and harder to maintain as it grows.

---

### 🔹 Version 2 – Modular Version (With Functions)

This version takes the initial concept and restructures it using *functions*, introducing better practices such as:

- *Code reusability*  
- *Separation of concerns*  
- *Better readability & maintainability*

Additionally, it introduces a basic form of *data persistence* by writing transaction logs to a .txt file (işlem_kaydı.txt), and includes a *menu-driven interface*.

> ✅ This version is more scalable and beginner-friendly for those moving toward object-oriented or modular Python projects.

---

## 🧪 Features (in both versions)

- 🔐 Secure login system with limited password attempts
- 💵 Cash withdrawal
- 💰 Cash deposit
- 📄 Balance inquiry
- 📁 Transaction logging (in version 2)
- 🚪 Exit and card return option

---

## 🧰 Technologies and Concepts Used

| Feature | Description |
|--------|-------------|
| input() | For interactive user input |
| while, if/elif/else | To control program flow and menus |
| try/except | To prevent crashes from invalid user input |
| getpass module | For hidden password input (version 1) |
| functions | Used in version 2 to separate logic |
| file I/O | Writes transaction logs to a file in version 2 |
| datetime | To timestamp each transaction in version 2 |

---

## 🚀 How to Run

1. Make sure you have Python installed (Python 3.6+ recommended).
2. Clone or download the repository.
3. Open a terminal and navigate to the project directory.
4. Run either version:

*Basic Version:*
```bash
python atm_no_function.py

Function-Based Version:

python atm_with_functions.py


---

🌱 Future Improvements

Add support for multiple users/accounts

Store user data securely in a database or file

Create a GUI using Tkinter or PyQt

Include account registration and password reset features

Add a logging system for debugging



---

🤝 Final Notes

This project was developed as part of a personal learning journey. While the first version laid the groundwork, the second version introduced better structure and scalability. Both versions serve as educational steps — not production-ready systems.

Feel free to fork, build on, or rewrite parts of it as you continue your Python learning journey!

> Happy coding 💻💡
