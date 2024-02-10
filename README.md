class AuthenticationSystem:
    def __init__(self):
        # Initialize a dictionary to store username-password pairs
        self.users = {}

    def register_user(self, username, password):
        # Register a new user with a username and password
        if username in self.users:
            print("Username already exists. Please choose a different one.")
        else:
            self.users[username] = password
            print("User registered successfully.")

    def login(self, username, password):
        # Authenticate user login
        if username in self.users and self.users[username] == password:
            print("Login successful. Welcome, {}!".format(username))
        else:
            print("Invalid username or password. Please try again.")


# Example usage
auth_system = AuthenticationSystem()

# Register new users
auth_system.register_user("user1", "password1")
auth_system.register_user("user2", "password2")

# Attempt login with correct and incorrect credentials
auth_system.login("user1", "password1")  # Successful login
auth_system.login("user2", "wrong_password")  # Failed login
