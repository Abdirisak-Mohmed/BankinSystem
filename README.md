import java.util.Scanner;

public class BankingSystem {
    double balance = 0;

    void deposit(double amount) {
        balance += amount;
        System.out.println("Deposited: $" + amount);
    }

    public void withdraw(double amount) {
        if (amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: $" + amount);
        } else {
            System.out.println("Not enough balance.");
        }
    }

    public void checkBalance() {
        System.out.println("Balance: $" + balance);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        BankingSystem account = new BankingSystem();
        int choice;

        do {
            System.out.println("\n1. Deposit\n2. Withdraw\n3. Check Balance\n4. Exit");
            System.out.print("Choose: ");
            choice = scanner.nextInt();

            if (choice == 1) {
                System.out.print("Amount to deposit: ");
                account.deposit(scanner.nextDouble());
            } else if (choice == 2) {
                System.out.print("Amount to withdraw: ");
                account.withdraw(scanner.nextDouble());
            } else if (choice == 3) {
                account.checkBalance();
            } else if (choice != 4) {
                System.out.println("Invalid choice.");
            }
        } while (choice != 4);

        System.out.println("Goodbye!");
        scanner.close();
    }
}
