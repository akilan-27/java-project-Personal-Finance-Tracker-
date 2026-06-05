import java.util.*;
import java.io.*;

public class PersonalFinanceTracker {

    static class Transaction {
        int id;
        String type;
        String category;
        String description;
        double amount;

        Transaction(int id, String type, String category,
                    String description, double amount) {
            this.id = id;
            this.type = type;
            this.category = category;
            this.description = description;
            this.amount = amount;
        }

        @Override
        public String toString() {
            return "ID:" + id + " | " + type + " | "
                    + category + " | " + description
                    + " | ₹" + amount;
        }
    }

    static Scanner sc = new Scanner(System.in);
    static ArrayList<Transaction> transactions = new ArrayList<>();
    static double monthlyBudget = 0;
    static int nextId = 1;

    public static void main(String[] args) {

        int choice;

        do {
            System.out.println("\n========== PERSONAL FINANCE TRACKER ==========");
            System.out.println("1. Set Monthly Budget");
            System.out.println("2. Add Income");
            System.out.println("3. Add Expense");
            System.out.println("4. View Transactions");
            System.out.println("5. Search Transaction");
            System.out.println("6. Delete Transaction");
            System.out.println("7. Financial Report");
            System.out.println("8. Category Report");
            System.out.println("9. Export Report");
            System.out.println("10. Save Data");
            System.out.println("11. Load Data");
            System.out.println("12. Exit");

            System.out.print("Enter Choice: ");
            choice = Integer.parseInt(sc.nextLine());

            switch (choice) {

                case 1:
                    setBudget();
                    break;

                case 2:
                    addIncome();
                    break;

                case 3:
                    addExpense();
                    break;

                case 4:
                    viewTransactions();
                    break;

                case 5:
                    searchTransaction();
                    break;

                case 6:
                    deleteTransaction();
                    break;

                case 7:
                    financialReport();
                    break;

                case 8:
                    categoryReport();
                    break;

                case 9:
                    exportReport();
                    break;

                case 10:
                    saveData();
                    break;

                case 11:
                    loadData();
                    break;

                case 12:
                    System.out.println("Thank You!");
                    break;

                default:
                    System.out.println("Invalid Choice");
            }

        } while (choice != 12);
    }

    static void setBudget() {
        System.out.print("Enter Monthly Budget: ₹");
        monthlyBudget = Double.parseDouble(sc.nextLine());
        System.out.println("Budget Updated!");
    }

    static void addIncome() {

        System.out.print("Income Source: ");
        String desc = sc.nextLine();

        System.out.print("Amount: ₹");
        double amount = Double.parseDouble(sc.nextLine());

        transactions.add(
                new Transaction(
                        nextId++,
                        "Income",
                        "Income",
                        desc,
                        amount));

        System.out.println("Income Added!");
    }

    static void addExpense() {

        System.out.println("\nCategories");
        System.out.println("1. Food");
        System.out.println("2. Travel");
        System.out.println("3. Shopping");
        System.out.println("4. Bills");
        System.out.println("5. Others");

        System.out.print("Select Category: ");

        int c = Integer.parseInt(sc.nextLine());

        String category;

        switch (c) {
            case 1:
                category = "Food";
                break;
            case 2:
                category = "Travel";
                break;
            case 3:
                category = "Shopping";
                break;
            case 4:
                category = "Bills";
                break;
            default:
                category = "Others";
        }

        System.out.print("Description: ");
        String desc = sc.nextLine();

        System.out.print("Amount: ₹");
        double amount = Double.parseDouble(sc.nextLine());

        transactions.add(
                new Transaction(
                        nextId++,
                        "Expense",
                        category,
                        desc,
                        amount));

        System.out.println("Expense Added!");
    }

    static void viewTransactions() {

        if (transactions.isEmpty()) {
            System.out.println("No Transactions Found!");
            return;
        }

        for (Transaction t : transactions) {
            System.out.println(t);
        }
    }

    static void searchTransaction() {

        System.out.print("Keyword: ");
        String key = sc.nextLine().toLowerCase();

        boolean found = false;

        for (Transaction t : transactions) {

            if (t.description.toLowerCase().contains(key)
                    || t.category.toLowerCase().contains(key)) {

                System.out.println(t);
                found = true;
            }
        }

        if (!found)
            System.out.println("No Match Found!");
    }

    static void deleteTransaction() {

        viewTransactions();

        System.out.print("Enter ID to Delete: ");
        int id = Integer.parseInt(sc.nextLine());

        Iterator<Transaction> it =
                transactions.iterator();

        while (it.hasNext()) {

            Transaction t = it.next();

            if (t.id == id) {

                it.remove();
                System.out.println("Deleted!");
                return;
            }
        }

        System.out.println("Transaction Not Found!");
    }

    static void financialReport() {

        double income = 0;
        double expense = 0;

        for (Transaction t : transactions) {

            if (t.type.equals("Income"))
                income += t.amount;
            else
                expense += t.amount;
        }

        double savings = income - expense;

        System.out.println("\n===== REPORT =====");
        System.out.println("Budget : ₹" + monthlyBudget);
        System.out.println("Income : ₹" + income);
        System.out.println("Expense: ₹" + expense);
        System.out.println("Savings: ₹" + savings);
        System.out.println("Remaining Budget: ₹"
                + (monthlyBudget - expense));
    }

    static void categoryReport() {

        HashMap<String, Double> map =
                new HashMap<>();

        for (Transaction t : transactions) {

            if (t.type.equals("Expense")) {

                map.put(
                        t.category,
                        map.getOrDefault(
                                t.category,
                                0.0)
                                + t.amount);
            }
        }

        System.out.println("\nExpense Category Report");

        for (String key : map.keySet()) {

            System.out.println(
                    key + " : ₹" + map.get(key));
        }
    }

    static void exportReport() {

        try {

            PrintWriter pw =
                    new PrintWriter(
                            "FinanceReport.txt");

            for (Transaction t : transactions) {

                pw.println(t);
            }

            pw.close();

            System.out.println(
                    "Report Exported Successfully!");
        }

        catch (Exception e) {

            System.out.println(
                    "Export Failed!");
        }
    }

    static void saveData() {

        try {

            ObjectOutputStream out =
                    new ObjectOutputStream(
                            new FileOutputStream(
                                    "finance.dat"));

            out.writeObject(
                    new ArrayList<>());

            out.close();

            System.out.println(
                    "Data Saved!");
        }

        catch (Exception e) {

            System.out.println(
                    "Save Failed!");
        }
    }

    static void loadData() {

        File file =
                new File("finance.dat");

        if (file.exists())
            System.out.println(
                    "Finance file found.");
        else
            System.out.println(
                    "No saved file found.");
    }
}