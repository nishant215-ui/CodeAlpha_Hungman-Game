# CodeAlpha_Hungman-Game
import random
words=["keyboard","python","sunset","rocket","planet"]
word=random.choice(words)
guessed=[]
tries=6
while tries>0:
    display="".join([l if l in guessed else "_" for l in word])
    print("Word:",display)
    if display==word:
        print("You guessed it:",word)
        break
    guess=input("Guess a letter: ").lower()
    if len(guess)!=1 or not guess.isalpha() or guess in guessed:
        continue
    guessed.append(guess)
    if guess not in word:
        tries-=1
        print("Wrong! Tries left:",tries)
if tries==0:
    print("Game Over! Word was:",word)
