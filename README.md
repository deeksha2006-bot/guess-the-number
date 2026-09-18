import random

def number_guessing_game():
    print(" Welcome to Number Guessing Game! ")
    number = random.randint(1, 100)  # computer picks a random number
    attempts = 0

    while True:
        guess = int(input("Guess a number between 1 and 100: "))
        attempts += 1

        if guess < number:
            print("Too low! Try again ")
        elif guess > number:
            print("Too high! Try again ")
        else:
            print("Correct! You guessed it in {attempts} tries ")
            break

# Run the game
number_guessing_game()
