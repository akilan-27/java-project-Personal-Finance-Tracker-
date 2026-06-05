# 💰 Personal Finance Tracker

A simple yet powerful **console-based Personal Finance Tracker** built using **Java**. This project helps users manage their finances by tracking income, expenses, budgets, savings, and generating financial reports.

Perfect for learning:

* ☕ Java Programming
* 🏗 Object-Oriented Programming (OOP)
* 📂 File Handling
* 📊 Data Management
* 🧠 Problem Solving
* 📝 Real-world Application Development

---

# ✨ Features

## 💵 Income Management

* Add income sources
* Track all earnings
* Maintain transaction history

## 💸 Expense Management

* Record expenses
* Categorize spending
* Track where money goes

### Available Categories

🍔 Food

🚗 Travel

🛍 Shopping

💡 Bills

📦 Others

---

## 🎯 Budget Management

* Set monthly budget
* Compare expenses with budget
* View remaining budget

---

## 🔍 Search Transactions

Search transactions by:

* Description
* Category

---

## 🗑 Delete Transactions

Remove incorrect or unwanted transactions using Transaction ID.

---

## 📊 Financial Reports

Generate reports showing:

* Total Income
* Total Expenses
* Savings
* Remaining Budget

---

## 📈 Category Reports

View spending distribution across categories.

Example:

```text
Food      : ₹2500
Travel    : ₹1800
Shopping  : ₹3200
Bills     : ₹1500
```

---

## 📄 Export Reports

Export all financial records to:

```text
FinanceReport.txt
```

for future reference.

---

# 🏗 Project Structure

Since this project uses a **single Java file**, everything is stored inside:

```text
PersonalFinanceTracker.java
```

This makes it:

* Easy to run
* Easy to submit
* Easy to upload on GitHub

No additional libraries required.

---

# ⚙ Technologies Used

| Technology    | Purpose            |
| ------------- | ------------------ |
| Java          | Core Development   |
| ArrayList     | Store Transactions |
| HashMap       | Category Reports   |
| File Handling | Export Reports     |
| OOP Concepts  | Data Management    |
| Scanner Class | User Input         |

---

# 🧠 Algorithms Used

## 1️⃣ Linear Search

Used in:

```java
searchTransaction()
```

Purpose:

* Find transactions by keyword.

Complexity:

```text
O(n)
```

---

## 2️⃣ Traversal Algorithm

Used in:

```java
financialReport()
categoryReport()
viewTransactions()
```

Purpose:

* Process all transactions.

Complexity:

```text
O(n)
```

---

## 3️⃣ HashMap Aggregation

Used in:

```java
categoryReport()
```

Purpose:

* Group expenses by category.

Complexity:

```text
O(n)
```

---

# 📚 Methods Used

| Method              | Purpose              |
| ------------------- | -------------------- |
| setBudget()         | Set monthly budget   |
| addIncome()         | Add income           |
| addExpense()        | Add expense          |
| viewTransactions()  | Display transactions |
| searchTransaction() | Search transactions  |
| deleteTransaction() | Delete transaction   |
| financialReport()   | Generate report      |
| categoryReport()    | Category analysis    |
| exportReport()      | Export to file       |
| saveData()          | Save finance data    |
| loadData()          | Load finance data    |

---

# 🔄 Project Workflow

```text
Start Program
      ↓
Set Budget
      ↓
Add Income
      ↓
Add Expenses
      ↓
Store Transactions
      ↓
Generate Reports
      ↓
Analyze Spending
      ↓
Export Report
      ↓
Exit
```

---

# 🎮 How To Use

## Step 1

Compile the program:

```bash
javac PersonalFinanceTracker.java
```

---

## Step 2

Run the program:

```bash
java PersonalFinanceTracker
```

---

## Step 3

Choose options from menu:

```text
1. Set Monthly Budget
2. Add Income
3. Add Expense
4. View Transactions
5. Search Transaction
6. Delete Transaction
7. Financial Report
8. Category Report
9. Export Report
10. Save Data
11. Load Data
12. Exit
```

---

# 🖥 Example Usage

### Set Budget

```text
Enter Monthly Budget: ₹10000
```

---

### Add Income

```text
Income Source: Internship
Amount: ₹15000
```

---

### Add Expense

```text
Category: Food
Description: Pizza
Amount: ₹500
```

---

### Financial Report

```text
Budget : ₹10000
Income : ₹15000
Expense: ₹5000
Savings: ₹10000
Remaining Budget: ₹5000
```

---

# 🚀 Future Improvements

Some advanced features that can be added:

* 🔐 Login System
* 📅 Monthly Tracking
* 📊 Expense Graphs
* 🏦 Bank Account Integration
* 📱 GUI using Java Swing
* ☁ Cloud Storage
* 🤖 AI Expense Prediction
* 📉 Spending Trend Analysis

---

# 🎓 Learning Outcomes

This project demonstrates:

✅ Object-Oriented Programming

✅ Collections Framework

✅ ArrayLists

✅ HashMaps

✅ File Handling

✅ Searching Algorithms

✅ Financial Calculations

✅ Console-Based UI

✅ Software Development Fundamentals

---

# 👨‍💻 Author

**R. Akilan**

🎓 B.Tech – Artificial Intelligence & Data Science

🏫 Kalaignar Karunanidhi Institute of Technology (KIT), Coimbatore

---

# ⭐ Support

If you found this project useful:

⭐ Star the repository

🍴 Fork the project

📢 Share with friends

💡 Suggest improvements

---

## 🎯 Project Goal

> "Helping users understand, track, and improve their personal finances through a simple Java-based financial management system."

💰 Track Smart • Save More • Spend Wisely 🚀
