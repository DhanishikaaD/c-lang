#include <stdio.h>

float balance = 1000.0; 

void checkBalance() {
    printf("\nYour current balance is: $%.2f\n", balance);
}

void deposit() {
    float amount;
    printf("\nEnter amount to deposit: $");
    scanf("%f", &amount);
    if (amount > 0) {
        balance += amount;
        printf("Successfully deposited $%.2f\n", amount);
        checkBalance();
    } else {
        printf("Invalid amount!\n");
    }
}

void withdraw() {
    float amount;
    printf("\nEnter amount to withdraw: $");
    scanf("%f", &amount);
    if (amount > 0 && amount <= balance) {
        balance -= amount;
        printf("Successfully withdrew $%.2f\n", amount);
        checkBalance();
    } else {
        printf("Invalid transaction!\n");
    }
}

int main() {
    int choice;
    while (1) {
        printf("\n--- ATM Menu ---\n");
        printf("1. Check Balance\n");
        printf("2. Deposit Money\n");
        printf("3. Withdraw Money\n");
        printf("4. Exit\n");
        printf("Choose an option: ");
        scanf("%d", &choice);
        
        switch (choice) {
            case 1:
                checkBalance();
                break;
            case 2:
                deposit();
                break;
            case 3:
                withdraw();
                break;
            case 4:
                printf("Thank you for using the ATM!\n");
                return 0;
            default:
                printf("Invalid choice, try again.\n");
        }
    }
    return 0;
}
