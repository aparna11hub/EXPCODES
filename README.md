EXP-1: Write a program to convert and print the distance in meters, feet, inches and centimeter.
CODE:
meters = float(input("Enter distance in meters: "))
centimeters = meters * 100
inches = meters * 39.3701
feet = meters * 3.28084
print("Distance in meters:", meters)
print("Distance in centimeters:", centimeters)
print("Distance in inches:", inches)
print("Distance in feet:", feet)

EXP-2: Create list consisting of Roll No., Name and Age. Perform various operations on list like add,
remove, count, concatenate etc. Also create tuple and dictionary and print the type of all.
CODE:
students = [[1, "Aparna", 21], [2, "Janhavi", 22], [3, "Shruti", 21]]
students.append([4, "Bhavesh", 23])
students.remove([2, "Janhavi", 22])
age_21_count = sum(1 for s in students if s[2] == 21)
new_students = [[5, "Bhavesh", 20]]
students += new_students
sample_tuple = ("Python", 3.11, True)
student_dict = {"Roll No.": 1, "Name": "Aparna", "Age": 20}
print("Students List:", students)
print("Count of age 21:", age_21_count)
print("List:", type(students))
print("Tuple:", type(sample_tuple))
print("Dictionary:", type(student_dict))

EXP 3: If ages of Ram, Shyam, and Ajay are given as an input through the keyboard, write a program to
determine the youngest of the three.
CODE:
ram = int(input("Enter age of Ram: "))
shyam = int(input("Enter age of Shyam: "))
ajay = int(input("Enter age of Ajay: "))

if ram < shyam and ram < ajay:
    print("Ram is the youngest.")
elif shyam < ram and shyam < ajay:
    print("Shyam is the youngest.")
else:
    print("Ajay is the youngest.")

EXP 4: Write python program to create add function to add arrays and use built in functions like add,
multiply, subtract and divide arrays.
CODE:
import numpy as np

def add(arr1, arr2):
    return np.add(arr1, arr2)

a = list(map(int, input("Enter first array: ").split()))
b = list(map(int, input("Enter second array: ").split()))

arr1 = np.array(a)
arr2 = np.array(b)

print("Addition:", add(arr1, arr2))
print("Subtraction:", np.subtract(arr1, arr2))
print("Multiplication:", np.multiply(arr1, arr2))
print("Division:", np.divide(arr1, arr2))

EXP 5: Use a for loop to print a triangle like the one below. Allow the user to specify how high the
triangle should be.
*
**
***
****
CODE:
height = int(input("Enter the height of the triangle: "))

for i in range(1, height + 1):
    print("*" * i)

EXP 6: Write a program to find the factorial value of any number entered through the keyboard.
CODE:
num = int(input("Enter a number: "))
fact = 1

for i in range(1, num + 1):
    fact *= i

print("Factorial:", fact)

EXP 7: Import tkinter package and all of its modules.
Create a root window. Give the root window a title and dimension.   Use mainloop() to call the
endless loop of the window. Add a label using the Label Class and change its text configuration
as desired.
CODE:
import tkinter as tk

root = tk.Tk()
root.title("Aparna's Tkinter Window")
root.geometry("400x300")

label = tk.Label(root, text="Hello, Tkinter!", font=("Arial", 16), fg="blue")
label.pack()

root.mainloop()

EXP 8: Use Python libraries like NumPy, Pandas, Matplotlib, SciPy, to plot points plot in various (2×2)
subplots.
CODE:
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from scipy.stats import norm

x = np.linspace(-5, 5, 100)
data = pd.Series(np.random.randn(100))

fig, axs = plt.subplots(2, 2, figsize=(8, 6))

axs[0, 0].plot(x, np.sin(x))
axs[0, 0].set_title('Sine Wave')

axs[0, 1].hist(data, bins=10, color='skyblue')
axs[0, 1].set_title('Histogram')

axs[1, 0].scatter(data.index, data)
axs[1, 0].set_title('Scatter Plot')

axs[1, 1].plot(x, norm.pdf(x))
axs[1, 1].set_title('Normal Dist')

plt.tight_layout()
plt.show()

EXP 9: Write a python program to obtain histogram by creating a function.
CODE:
import matplotlib.pyplot as plt

def create_histogram():
    data = input("Enter numbers separated by space: ")
    numbers = list(map(int, data.split()))
    
    bins = int(input("Enter the number of bins: "))
    
    plt.hist(numbers, bins=bins, color='lightblue', edgecolor='black')
    plt.title("Histogram")
    plt.xlabel("Values")
    plt.ylabel("Frequency")
    plt.show()

create_histogram()

EXP 10: Write a program for linear regression using python
CODE:
from sklearn.linear_model import LinearRegression
import numpy as np
import matplotlib.pyplot as plt

x = np.array([1, 2, 3, 4, 5]).reshape(-1, 1)
y = np.array([2, 4, 5, 4, 5])

model = LinearRegression()
model.fit(x, y)

y_pred = model.predict(x)

plt.scatter(x, y, color='blue', label='Actual')
plt.plot(x, y_pred, color='red', label='Predicted')
plt.xlabel('X')
plt.ylabel('Y')
plt.title('Linear Regression')
plt.legend()
plt.show()

EXP 11: Write a class called Time whose only field is a time in seconds. It should have a method called
convert_to_minutes that returns a string of minutes and seconds formatted as in the following example:
if seconds is 230, the method should return &#39;5:50&#39;. It should also have a method called convert_to_hours
that returns a string of hours, minutes, and seconds formatted analogously to the previous method.
CODE:
class Time:
    def __init__(self, seconds):
        self.seconds = seconds

    def convert_to_minutes(self):
        return f"{self.seconds // 60}:{self.seconds % 60:02d}"

    def convert_to_hours(self):
        return f"{self.seconds // 3600}:{(self.seconds % 3600) // 60:02d}:{self.seconds % 60:02d}"

# User input for time in seconds
time_in_seconds = int(input("Enter time in seconds: "))
time_obj = Time(time_in_seconds)

print(f"Time in minutes and seconds: {time_obj.convert_to_minutes()}")
print(f"Time in hours, minutes, and seconds: {time_obj.convert_to_hours()}")
