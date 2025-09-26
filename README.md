import random

word_bank = ["python", "java", "kotlin", "javascript"]
word = random.choice(word_bank)
guessed_word = ["_"] * len(word)

attempts = 6  # set number of attempts

while attempts > 0:
    print('\nCurrent word: ' + ' '.join(guessed_word))
    guess = input('Guess a letter: ').lower()

    if guess in word:
        for i in range(len(word)):
            if word[i] == guess:
                guessed_word[i] = guess
    else:
        attempts -= 1
        print('Incorrect! Attempts left: ' + str(attempts))

    if "_" not in guessed_word:
        print('Congratulations! You guessed the word: ' + word)
        break

    if attempts == 0 and "_" in guessed_word:
        print('Game over! The word was: ' + word)
        break
    
