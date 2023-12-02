#include <iostream>

class BankAccount {
private:
    std::string accountHolderName;
    double balance;

public:
    BankAccount(std::string name, double initialBalance) {
        accountHolderName = name;
        balance = initialBalance;
    }

    
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            std::cout << "Deposited $" << amount << " successfully.\n";
        } else {
            std::cout << "Invalid deposit amount.\n";
        }
    }


    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            std::cout << "Withdrawn $" << amount << " successfully.\n";
        } else {
            std::cout << "Invalid withdrawal\n";
        }
    }

    // Method to check the account balance
    void checkBalance() {
        std::cout << "Account Balance for " << accountHolderName << ": $" << balance << "\n";
    }
};

int main() {
    // Creating a BankAccount object with an initial balance of $1000
    BankAccount myAccount("mohan", 1000.0);

    myAccount.checkBalance(); 
    myAccount.deposit(500.0); 
    myAccount.checkBalance(); 
    myAccount.withdraw(200.0); 
    myAccount.checkBalance();
    myAccount.withdraw(1500.0); 
    myAccount.checkBalance(); 

    return 0;
}
