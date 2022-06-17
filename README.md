# Basic-Calculator-in-Python


import tkinter as tk
from tkinter.constants import SUNKEN
import tkinter.messagebox

mainWindow = tk.Tk()
mainWindow.title("Calculator")
frame = tk.Frame(master=mainWindow, bg="pink", padx=10)
frame.pack()
entry = tk.Entry(master=frame, relief=SUNKEN, borderwidth=5, width=30)
entry.grid(row=0, column=0, columnspan=3, ipady=2, pady=2)


def click(data):
    entry.insert(tk.END, data)


def clear():
    entry.delete(0, tk.END)

def calculate():
    try:
        ans = str(eval(entry.get()))
        entry.delete(0, tk.END)
        entry.insert(0, ans)
    except:
        tkinter.messagebox.showinfo("Error", "Syntax Error!")


# ROW 1
button_1 = tk.Button(master=frame, text="1", padx=10, pady=5, width=3, command=lambda: click(1))
button_1.grid(row=1, column=0, pady=2)

button_2 = tk.Button(master=frame, text="2", padx=10, pady=5, width=3, command=lambda: click(2))
button_2.grid(row=1, column=1, pady=2)

button_3 = tk.Button(master=frame, text="3", padx=10, pady=5, width=3, command=lambda: click(3))
button_3.grid(row=1, column=2, pady=2)

# ROW 2
button_4 = tk.Button(master=frame, text="4", padx=10, pady=5, width=3, command=lambda: click(4))
button_4.grid(row=2, column=0, pady=2)

button_5 = tk.Button(master=frame, text="5", padx=10, pady=5, width=3, command=lambda: click(5))
button_5.grid(row=2, column=1, pady=2)

button_6 = tk.Button(master=frame, text="6", padx=10, pady=5, width=3, command=lambda: click(6))
button_6.grid(row=2, column=2, pady=2)

# ROW 3
button_7 = tk.Button(master=frame, text="7", padx=10, pady=5, width=3, command=lambda: click(7))
button_7.grid(row=3, column=0, pady=2)

button_8 = tk.Button(master=frame, text="8", padx=10, pady=5, width=3, command=lambda: click(8))
button_8.grid(row=3, column=1, pady=2)

button_9 = tk.Button(master=frame, text="9", padx=10, pady=5, width=3, command=lambda: click(9))
button_9.grid(row=3, column=2, pady=2)


# ROW 4
button_0 = tk.Button(master=frame, text="0", padx=10, pady=5, width=3, command=lambda: click(0))
button_0.grid(row=4, column=0, pady=2)

button_clear = tk.Button(master=frame, text="C", padx=10, pady=5, width=3, command=lambda: clear())
button_clear.grid(row=4, column=1, pady=2)

button_add = tk.Button(master=frame, text="+", padx=10, pady=5, width=3, command=lambda: click("+"))
button_add.grid(row=4, column=2, pady=2)

# ROW 5
button_div = tk.Button(master=frame, text="/", padx=10, pady=5, width=3, command=lambda: click("/"))
button_div.grid(row=5, column=0, pady=2)

button_mul= tk.Button(master=frame, text="*", padx=10, pady=5, width=12, command=lambda: click("*"))
button_mul.grid(row=5, column=1, columnspan=2, pady=2)

#ROW 6
button_sub = tk.Button(master=frame, text="-", padx=10, pady=5, width=3, command=lambda: click("-"))
button_sub.grid(row=6, column=0, pady=2)

button_mul = tk.Button(master=frame, text="=", padx=10, pady=5, width=12, command=lambda: calculate())
button_mul.grid(row=6, column=1, columnspan=2, pady=2)

mainWindow.mainloop()


