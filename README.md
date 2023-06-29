import random #importing random liberary    
def hangman(): #creating hangman function

    list_of_words = ['education' , 'hangman' , 'aman' , 'smaller' , 'hang' , 'random' , 'india'] # list of main words 
    word = random.choice(list_of_words)  # random.choice is an inbult function that choose random function from list 
    turns = 10 # total no of turns 
    guess_made = "" # for gussing the word 
    valid_entries = set("abcdefghijklmnopqrstuvwxyz") #set basically make the alphabet in list 

    while len(word)>0: #length of word 
        main_word = ""  
# if we choose the word that is in word list then it will add the word into main word  
        for letter in word:
            if letter in guess_made:
                main_word = main_word+letter
            else:
                main_word = main_word + "_ "
# if main word == word then print won 
        if main_word == word:
            print(main_word)
            print("you won!!!!!!")
            break
#taking guess as input 
        print("Guess the word" , main_word)
        guess = input()

        if guess in valid_entries:
            guess_made = guess_made+guess
        else:
            print("Enter valid charater:-")
            guess = input()

        if guess not in word:
            turns = turns-1
# hangman creation 
        if turns == 9:
            print("Only 9 turns are left !!!")
            print("---------------------------")
        if turns == 8:
            print("Only 8 turns are left !!!")
            print("---------------------------")
            print("          O                ")
        if turns == 7:
            print("Only 7 turns are left !!!")
            print("---------------------------")
            print("          O                ")
            print("          |                ")
        if turns == 6:
            print("Only 6 turns are left !!!")
            print("---------------------------")
            print("          O                ")
            print("          |                ")
            print("         /                 ")
        if turns == 5:
            print("Only 5 turns are left !!!")
            print("---------------------------")
            print("          O                ")
            print("          |                ")
            print("         / \                ")

        if turns == 4:
            print("Only 4 turns are left !!!")
            print("---------------------------")
            print("         \O                ")
            print("          |                ")
            print("         / \               ")
            

        if turns == 3:
            print("Only 3 turns are left !!!")
            print("---------------------------")
            print("         \O/               ")
            print("          |                ")
            print("         / \               ")
        if turns == 2:
            print("Only 2 turns are left !!!")
            print("---------------------------")
            print("         \O/ |               ")
            print("          |                ")
            print("         / \               ")
        if turns == 1:
            print("Only 1 turns are left !!! Hangman is on his last breath, you are loosing the game")
            print("---------------------------")
            print("         \O/_|               ")
            print("          |                ")
            print("         / \               ")

        if turns == 0:
            print("You loose!!!!!!!")
            print("You let a greatman die!!!")
            print("---------------------------")
            print("          O _|               ")
            print("         /|\                ")
            print("         / \               ")
            break

   
name = input("Enter your name -> ")
print("Welcome", name , "to this amazing hangman game !!")
print("------------------------------------------------------------")
print("Try to guess the word in less then 10 attempts" , name)
hangman()
