#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

// Function to generate a random number
int generateRandomNumber() {
    srand(time(0));
    return rand() % 100 + 1;
}

// Function to check the user's guess
void checkGuess(int target) {
    int userInput;
    
    cout << "Guess a number between 1 and 100: ";
    
    while (true) {
        cin >> userInput;
        
        if (userInput > target) {
            cout << "Too high! Try again: ";
        } else if (userInput < target) {
            cout << "Too low! Try again: ";
        } else {
            cout << "Congratulations! You guessed it right.\n";
            break;
        }
    }
}

int main() {
    int secretNumber = generateRandomNumber(); // Generate a random number
    checkGuess(secretNumber); // Start the guessing process
    return 0;
}
