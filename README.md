# secure-password-maker
Author - Arushi Jain
import random
import string
def generatePassword(length = 6):
    character = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(character) for _ in range(length))
    return password
print("Welcome to Password Generator: ")
recovery_question = input("Set a recovery question in case you forget the password: ") 
recovery_answer = input("Set the answer to your recovery question: ").strip().lower()
password = generatePassword()
print("\nYour password has been generated successfully.")
while True:
    print("\nOptions")
    print("1. View password")
    print("2. Generate Password")
    print("3. Exit")
    
    choice = int(input("Enter your choice 1/2/3: "))
    
    if choice == 1:
        a = input("Enter the password: ")
        if a != password:
            print("Invalid Password")
            print("\n4. Forgot Password")
            choice1 = int(input("Enter your choice [Select option 4 to know the password]: "))
            if choice1 == 4:
                answer = input(f"{recovery_question} ").strip().lower()
                if answer == recovery_answer:
                    print(f"Your password is: {password}")
                else:
                    print("Recovery answer incorrect. Access denied!")
            else:
                print("Invalid choice!")
        else:
            print(f"Correct! Your password is: {password}")
    
    elif choice == 2:
        password = generatePassword()
        print("New password generated and saved successfully!")

    elif choice == 3:
        print("Exiting!!")
        break
    else:
        print("Invalid choice!")

            
