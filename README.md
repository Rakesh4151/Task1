# Task1
import random

def hangman():
    word = random.choice(['python', 'java', 'code', 'codealpha'])
    guessed = ["_"] * len(word)
    attempts = 6

    print("Welcome to Hangman!")
    
    while attempts > 0 and "_" in guessed:
        print(" ".join(guessed))
        guess = input("Guess a letter: ")

        if guess in word:
            for i, letter in enumerate(word):
                if letter == guess:
                    guessed[i] = letter
        else:
            attempts -= 1
            print(f"Incorrect! {attempts} attempts left.")

        # Stop if all letters are guessed
        if "_" not in guessed:
            print(" ".join(guessed))
            print("Congratulations! You guessed the word.")
            return
    
    print(f"Game Over! The word was '{word}'.")

hangman()
