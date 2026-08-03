import random

words = ["python", "apple", "computer", "college", "banana"]

word = random.choice(words)


display = ["_"] * len(word)


guessed = []


wrong_guesses = 0
max_wrong = 6

print("===== HANGMAN GAME =====")

while wrong_guesses < max_wrong and "_" in display:
    print("\nWord:", " ".join(display))
    print("Wrong guesses left:", max_wrong - wrong_guesses)

    guess = input("Enter a letter: ").lower()

  
    if guess in guessed:
        print("You already guessed that letter.")
        continue

    guessed.append(guess)

    
    if guess in word:
        print("Correct!")

        
        for i in range(len(word)):
            if word[i] == guess:
                display[i] = guess
    else:
        print("Wrong!")
        wrong_guesses += 1


if "_" not in display:
    print("\nCongratulations! You guessed the word:", word)
else:
    print("\nGame Over!")
    print("The correct word was:", word)
