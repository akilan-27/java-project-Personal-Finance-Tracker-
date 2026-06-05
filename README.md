💰 Personal Finance Tracker
A lightweight, console-based Java application designed to help you manage your monthly budget, track income and expenses, and generate financial reports—all without needing an external database.

🚀 Features
Budget Management: Set and track your monthly budget limits.

Transaction Handling: Easily add, view, and delete income or expense entries.

Categorized Expenses: Track spending across categories like Food, Travel, Shopping, and Bills.

Search Functionality: Quickly find specific transactions using keywords.

Reporting: Generate financial summaries (Income vs. Expense) and breakdown reports by category.

Export/Save: Export your financial history to a text file or save data locally.

🛠️ Prerequisites
Java Development Kit (JDK): Ensure you have JDK 8 or higher installed on your system.

🚀 How to Run
Download the File: Save PersonalFinanceTracker.java to a folder on your computer.

Compile the Code: Open your terminal or command prompt in that folder and run:

Bash
javac PersonalFinanceTracker.java
Run the Application:

Bash
java PersonalFinanceTracker
💡 Usage Guide
Once the application is running, you will see a menu. Simply type the number corresponding to the action you wish to perform:

Set Monthly Budget (1): Enter your total budget for the month.

Add Income/Expense (2 & 3): Follow the prompts to enter the source/category, description, and amount.

View Transactions (4): See a complete list of your financial activity.

Search (5): Type a keyword (e.g., "Food") to filter your transactions.

Reports (7 & 8): View your overall savings or a breakdown of where your money is going by category.

Export (9): Saves a clean list of your transactions into FinanceReport.txt.

Save/Load (10 & 11): Manage your data persistence locally.

📂 File Structure
PersonalFinanceTracker.java — The source code.

FinanceReport.txt — Generated automatically when you choose the Export option.

finance.dat — Created when you save your data to keep your progress.

👤 Author
[Your Name] Portfolio Project

License: This project is open for educational use.

A small note on your code:
I noticed that in your saveData() method, you are currently writing an empty new ArrayList<>() to the file instead of the actual transactions list.

Make sure to change this line:

Java
out.writeObject(new ArrayList<>()); // This saves an empty list!
To this:

Java
out.writeObject(transactions); // This saves your actual data
