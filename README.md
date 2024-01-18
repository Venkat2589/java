import java.util.Scanner;

class Cust {
    String name;
    long accountNumber;
    double balance;

    public Cust(String name, long accountNumber, double balance) {
        this.name = name;
        this.accountNumber = accountNumber;
        this.balance = balance;
    }
    public void displayDetails() {
        System.out.println("Customer Details:");
        System.out.println("Name: " + name);
        System.out.println("Account Number: " + accountNumber);
        System.out.println("Balance: $" + balance);
    }
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposit successful "+ balance);
        } else {
            System.out.println("Invalid amount!");
        }
    }
}

class Bankingproblem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("enter no of customers: ");
        int no_of_customers = scanner.nextInt();
        Customer[] customers = new Customer[no_of_customers];
        for(int i=0;i<no_of_customers;i++) {
            System.out.println("Enter customer name: ");
            String name = scanner.next();

            System.out.print("Enter account number: ");
            long accountNumber = scanner.nextLong();

            System.out.print("Enter deposit amount:");
            double Deposit = scanner.nextDouble();

            customers[i] = new Customer(name, accountNumber, Deposit);
        }

        for (Customer custom : customers) {
                custom.displayDetails();
                System.out.print("Enter deposit amount : ");
                double depositAmount = scanner.nextDouble();
                custom.deposit(depositAmount);
        }
            scanner.close();
    }
}
