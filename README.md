# PASSWORD-STRENGTH-CHECKER-
A password strength checker project is a software tool designed to evaluate the security of user entered passwords by analysing criteria like length, character variety, and complexity, then providing feedback.

def check_password_strength(password):
    strength = 0
    # Length check
    if len(password) >= 8:
        strength += 1
    # Uppercase letter check
    if any(char.isupper() for char in password):
        strength += 1
    # Lowercase letter check
    if any(char.islower() for char in password):
        strength += 1
    # Digit check
    if any(char.isdigit() for char in password):
        strength += 1
    # Special character check
    if any(char in "!@#$%^&*()" for char in password):
        strength += 1
    # Strength result
    if strength <= 2:
        return "Weak Password"
    elif strength == 3 or strength == 4:
        return "Medium Password"
    else:
        return "Strong Password"
password = input("Enter your password : ")
result = check_password_strength(password)
print("Password Strength:",result)
