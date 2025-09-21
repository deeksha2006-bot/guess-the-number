import random

def number_guessing_game():
    print("🎲 Welcome to the Number Guessing Mini Project! 🎲")
    print("Select difficulty level:")
    print("1. Easy (1-10)")
    print("2. Medium (1-50)")
    print("3. Hard (1-100)")
    level = input("Enter 1, 2, or 3: ")

    if level == "1":
        max_num = 10
    elif level == "2":
        max_num = 50
    else:
        max_num = 100

    number = random.randint(1, max_num)
    attempts = 0

    while True:
        try:
            guess = int(input(f"Guess a number between 1 and {max_num}: "))
            if guess < 1 or guess > max_num:
                print(f"Please guess a number within the range 1 to {max_num}.")
                continue
        except ValueError:
            print("Invalid input! Please enter an integer.")
            continue

        attempts += 1

        if guess < number:
            print("Too low! Try again ⬇️")
        elif guess > number:
            print("Too high! Try again ⬆️")
        else:
            print(f"🎉 Correct! You guessed it in {attempts} tries 🎉")
            break

    return attempts

def main():
    best_score = None
    while True:
        score = number_guessing_game()
        if best_score is None or score < best_score:
            best_score = score
            print(f"🏆 New best score: {best_score} attempts!")
        play_again = input("Play again? (y/n): ").lower()
        if play_again != 'y':
            print("Thanks for playing! 👋")
            break

if __name__ == "__main__":
    main()
