import math
import pandas as pd
import matplotlib.pyplot as plt

def quadratic_solver(a, b, c):
    # Calculate the discriminant
    discriminant = b**2 - 4*a*c
   
    # Check if the discriminant is positive, zero, or negative
    if discriminant > 0:
        root1 = (-b + math.sqrt(discriminant)) / (2*a)
        root2 = (-b - math.sqrt(discriminant)) / (2*a)
        return root1, root2
    elif discriminant == 0:
        root = -b / (2*a)
        return root, root
    else:
        return None

def solve_weather_equation(a, b, c):
    solutions = quadratic_solver(a, b, c)
    return solutions

def plot_weather_model(a, b, c):
    # Calculate the discriminant
    discriminant = b**2 - 4*a*c

    # Check if there are real roots before plotting
    if discriminant >= 0:
        x = range(-4, 4)  # Range of x values
        y = [a * (i**2) + b * i + c for i in x]  # Calculate y values based on quadratic equation

        plt.figure(figsize=(8, 6))
        plt.plot(x, y, label=f"{a}x^2 + {b}x + {c}")  # Plot the quadratic function
        plt.axhline(0, color='black',linewidth=0.5)
        plt.axvline(0, color='black',linewidth=0.5)
        plt.title('Weather Model')
        plt.xlabel('X')
        plt.ylabel('Y')
        plt.legend()
        plt.grid(True)
        plt.show()
    else:
        print("No real roots. Cannot plot the graph.")


def main():
    choice = input("Choose an option:\n1. Hard-coded variables\n2. Keyboard input\n3. Read from a file\n")

    if choice == '1':
        # Hard-coded coefficients for a quadratic equation representing a weather model
        a = 2
        b = -7
        c = 3
        solutions = solve_weather_equation(a, b, c)
        print("Solutions:", solutions)
        plot_weather_model(a, b, c)
       
    elif choice == '2':
        # Take coefficients from user input
        a = float(input("Enter coefficient a: "))
        b = float(input("Enter coefficient b: "))
        c = float(input("Enter coefficient c: "))
        solutions = solve_weather_equation(a, b, c)
        print("Solutions:", solutions)
        plot_weather_model(a, b, c)
       
    elif choice == '3':
        try:
            filename = input("Enter the file name with coefficients (e.g., coefficients.txt): ")
            with open(filename, 'r') as file:
                lines = file.readlines()
                for line in lines:
                    coefficients = list(map(float, line.split()))
                    a, b, c = coefficients
                    solutions = solve_weather_equation(a, b, c)
                    print(f"Coefficients: {coefficients} -> Solutions: {solutions}")
                    plot_weather_model(a, b, c)
        except FileNotFoundError:
            print("File not found. Please provide a valid file name.")
       
    else:
        print("Invalid choice. Please select 1, 2, or 3.")

if __name__ == "__main__":
    main()
