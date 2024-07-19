#PRODIGY_CS_03

Welcome to PRODIGY_CS_03! This is a project that aims to allow users to check the strength of their passwords.

## Function

The password strength checker program works on the following:
1. Takes 'text' as inputs.
2. Iterates through each character on the text to check for number of uppercases, lowercases, special characters and digits.
3. It calculates the number of  uppercases, lowercases, special characters and digits, and adds points accordingly
4. Checks if the entered passwordis found in the common list of passwords.
5. Returns the strength score.


## Usage

1. Allows the user to enter the password.
   ```
   password = input(("Enter Your Password: "))
   #password = ""
   uppercase = any(c in string.ascii_uppercase for c in password)
   lowercase = any(c in string.ascii_lowercase for c in password)
   special = any(c in string.punctuation for c in password)
   digits = any(c in string.digits for c in password)

   characters = [uppercase, lowercase, special, digits]
   length = len(password)
   score = 0
   ```
2.  Reads common passwords from the file and compares it with the users password.
   ```
   with open('common.txt', 'r') as f:
    common = f.read().splitlines()

   if password in common:
    print("Password was found in a common list. Score: 0/10")
    exit()
   ``` 
3. Checks the password strength based on length. 
   ```
    if length > 8:
      score += 1
    if length > 12:
      score += 1
    if length > 17:
      score += 1
    if length > 20:
      score += 1
   print(f"Password Length is {length}, adding {score} points!")

   ```
4. Checks the password strength based on character diversity.
   ```
    if sum(characters) > 1:
      score += 1
    if sum(characters) > 2:
      score += 1
    if sum(characters) > 3:
      score += 1

    print(f"Password has {sum(characters)} different character types, adding {sum(characters) - 1} points!")
   ```
5. Calculates the final score.
   ```
   if score <= 4:
    print(f"The password is quite weak! Score: {score}/10")
    elif score >4 and score <= 6:
    print(f"The password is moderate! Score: {score}/10")
    else:
    print(f"The password is strong! Score: {score}/10")
   
  ```

## Output

![Screenshot (472)](https://github.com/user-attachments/assets/dbaf4249-a1fe-476f-8384-f4fdad0945ce)



Happy coding!
