#include <iostream>
#include <limits>
using namespace std;

// Define color codes
#define RESET   "\033[0m"
#define RED     "\033[31m"
#define GREEN   "\033[32m"
#define YELLOW  "\033[33m"
#define BLUE    "\033[34m"
#define MAGENTA "\033[35m"
#define CYAN    "\033[36m"

void displayMenu() {
    cout << YELLOW << "\n===== SIMPLE CALCULATOR =====\n" << RESET;
    cout << GREEN << "1. Addition (+)\n" << RESET;
    cout << CYAN << "2. Subtraction (-)\n" << RESET;
    cout << MAGENTA << "3. Multiplication (*)\n" << RESET;
    cout << BLUE << "4. Division (/)\n" << RESET;
    cout << RED << "5. Exit\n" << RESET;
    cout << YELLOW << "============================\n" << RESET;
    cout << GREEN << "Enter your choice (1-5): " << RESET;
}

double getNumber(const string& prompt) {
    double num;
    while (true) {
        cout << CYAN << prompt << RESET;
        cin >> num;
        if (cin.fail()) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
            cout << RED << "Invalid input. Please enter a number.\n" << RESET;
        } else {
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
            return num;
        }
    }
}

int main() {
    int choice;
    double num1, num2, result;
    bool running = true;

    while (running) {
        displayMenu();
        cin >> choice;

        // Handle invalid menu choices
        if (cin.fail() || choice < 1 || choice > 5) {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
            cout << RED << "Invalid choice. Please enter a number between 1 and 5.\n" << RESET;
            continue;
        }

        if (choice == 5) {
            cout << MAGENTA << "\nThank you for using the calculator. Goodbye!\n" << RESET;
            running = false;
            continue;
        }

        num1 = getNumber("Enter first number: ");
        num2 = getNumber("Enter second number: ");

        switch (choice) {
            case 1: // Addition
                result = num1 + num2;
                cout << GREEN << "\nResult: " << num1 << " + " << num2 << " = " << result << "\n" << RESET;
                break;
            case 2: // Subtraction
                result = num1 - num2;
                cout << CYAN << "\nResult: " << num1 << " - " << num2 << " = " << result << "\n" << RESET;
                break;
            case 3: // Multiplication
                result = num1 * num2;
                cout << MAGENTA << "\nResult: " << num1 << " * " << num2 << " = " << result << "\n" << RESET;
                break;
            case 4: // Division
                if (num2 == 0) {
                    cout << RED << "\nError: Division by zero is not allowed.\n" << RESET;
                } else {
                    result = num1 / num2;
                    cout << BLUE << "\nResult: " << num1 << " / " << num2 << " = " << result << "\n" << RESET;
                }
                break;
        }
    }

    return 0;
}
