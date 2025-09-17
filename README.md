# guessword
Give it a try
import random
word_bank=["sigma","insta","mentality","post-replication","kanak","python","hangman","challenge","programming","development","function","variable","iteration","condition","loop","array","string","integer","float","boolean"]
word=random.choice(word_bank)
guessedword=['_']*len(word)
attempts=12
while attempts>0:
    print('\nCurrent word:'+''.join(guessedword))
    guess=input("Guess a letter: ").lower()
    if guess in word:
        for i in range(len(word)):
            if word[i]==guess:
                guessedword[i]=guess
            print("Correct guess!")
        else:
            attempts-=1
            print("Wrong guess! Attempts left:"+ str(attempts))
    if '_' not in guessedword:
        print("Congratulations! You've guessed the word:"+word)
        break
    if attempts==0 and '_' in guessedword:
        print("Game over! The word was:"+word)
        while attempts>0:
            print('\nCurrent word:'+''.join(guessedword))
            guess=input("Guess a letter: ").lower()
            if guess in word:
                for i in range(len(word)):
                    if word[i]==guess:
                        guessedword[i]=guess
                print("Correct guess!")
            else:
                attempts-=1
                print("Wrong guess! Attempts left:"+ str(attempts))
            if '_' not in guessedword:
                print("Congratulations! You've guessed the word:"+word)
                break
            if attempts==0 and '_' in guessedword:
                print("Game over! The word was:"+word)
