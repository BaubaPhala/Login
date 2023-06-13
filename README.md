# Login
import tkinter as tk
from tkinter import messagebox


# Function to check if the login is successful
def login():
    username = entry_username.get()
    password = entry_password.get()

    # You can modify this condition to match your authentication logic
    if username == "bauba" and password == "phala":
        messagebox.showinfo("Login Successful", "Welcome, " + username + "!")
        # Open the personal page
        open_personal_page()
    else:
        messagebox.showerror("Login Failed", "Invalid username or password")


# Function to open the personal page
def open_personal_page():
    # Destroy the login page and create the personal page
    login_page.destroy()

    personal_page = tk.Tk()
    personal_page.title("Personal Page")
    personal_page.geometry("500x300")

    # Personal page widgets
    label_personal = tk.Label(personal_page, text="This is your personal page!")
    label_personal.pack(pady=10)
    label_personal.geometry("500x300")

    personal_page.mainloop()


# Function to open the registration page
def open_registration_page():
    # Destroy the login page and create the registration page
    login_page.destroy()

    registration_page = tk.Tk()
    registration_page.title("Registration Page")
    registration_page.geometry("500x300")

    # Registration page widgets
    label_registration = tk.Label(registration_page, text="Registration Page")
    label_registration.pack(pady=10)

    registration_page.mainloop()


# Create the main login page
login_page = tk.Tk()
login_page.title("Login Page")
login_page.geometry("500x300")

# Login page widgets
label_username = tk.Label(login_page, text="Username:")
label_username.pack()
entry_username = tk.Entry(login_page)
entry_username.pack(pady=5)

label_password = tk.Label(login_page, text="Password:")
label_password.pack()
entry_password = tk.Entry(login_page, show="*")
entry_password.pack(pady=5)

button_login = tk.Button(login_page, text="Login", command=login)
button_login.pack(pady=10)

button_register = tk.Button(login_page, text="Register", command=open_registration_page)
button_register.pack()

login_page.mainloop()
