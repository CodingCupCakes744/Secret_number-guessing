import random

def game():
    secret_number = random.randint(1, 50) 
    attempts = 1  # Initialize the attempts 

    print("Welcome to the Secret Number Guessing Game!")
    print("Try to guess the secret number between 1 and 50. You'll get hints after each guess.")
    
    
    guess = int(input(f"Attempt {attempts}: Guess a number between 1 and 50: "))
    
    while True:
        attempts += 1  # Increment the attempt counter
        
        # Option for the player to reveal the answer after 4 attempts
        if attempts == 4:
            UI = input("At any point, you can type '7129' to know the answer. Wanna know it now? Yes/No: ").strip().lower()
            if UI == "yes":
                print(f"The secret number was: {secret_number}")
                break  # Exit the loop after revealing the answer
            if UI == "no":
                print("Alright,continue!")     

        
        if guess == secret_number:
            print(f"Woah, it was indeed {secret_number}, you got it right in {attempts} attempts!")
            choice = input("Wanna play again? Yes/No: ").strip().lower()
            if choice == "yes":
                game()  
            elif choice == "no":
                print("Goodbye! Hope to see you again soon!")
                break  

        
        elif guess > secret_number:
            print("Too high! Try again: ")
            guess = int(input(f"Attempt {attempts}: "))
            if guess == 7129:
                print(f"The secret number was {secret_number}")
                break  

        
        elif guess < secret_number:
            print("Too low! Try again: ")
            guess = int(input(f"Attempt {attempts}: "))
            if guess == 7129:
                print(f"The secret number was {secret_number}")
                break  

game()

"""I just wanna say that this is not AI generated...I created the code myself and understand how it works and I only used AI for making the dialogues better"""