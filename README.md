import tkinter as tk
from tkinter import messagebox
from tkinter import *

def submit_order():
    # Validate required fields
    if not customer_name.get() or not product_name.get()or not product_description.get() or not quantity.get():
        messagebox.showerror("Error", "Please fill in all required fields.")
        return
    # Generate sales order
    order_info = f"Sales Order"

customer_name:{customer_name.get()}
product_name:{product_name.get()}
description:{description.get()}
quantity: {quantity.get()}

    # Add optional fields
if date.get():
    order_info += f"Date: {date.get()}\n"
if signature.get():
    order_info += f"Signature: {signature.get()}\n"
if phone.get():
    order_info += f"Phone No: {phone.get()}\n"
    
    # Print or save the sales order
    # print(order_info)

# Create tkinter window
window = tk.Tk()
window.title("Sales Order System")

# Create labels and entry fields
tk.Label(window, text="Customer Name:").grid(row=0, column=0, sticky="W")
customer_name = tk.StringVar()
tk.Entry(window, textvariable=customer_name).grid(row=0, column=1)

tk.Label(window, text="Product Name:").grid(row=1, column=0, sticky="W")
product_name = tk.StringVar()
tk.Entry(window, textvariable=product_name).grid(row=1, column=1)

tk.Label(window, text="Product Description:").grid(row=2, column=0, sticky="W")
product_description = tk.StringVar()
tk.Entry(window, textvariable=product_description).grid(row=2, column=1)

tk.Label(window, text="Quantity:").grid(row=3, column=0, sticky="W")
quantity = tk.StringVar()
tk.Entry(window, textvariable=quantity).grid(row=3, column=1)

tk.Label(window, text="Date:").grid(row=4, column=0, sticky="W")
date = tk.StringVar()
tk.Entry(window, textvariable=date).grid(row=4, column=1)

tk.Label(window, text="Signature:").grid(row=5, column=0, sticky="W")
signature = tk.StringVar()
tk.Entry(window, textvariable=signature).grid(row=5, column=1)

tk.Label(window, text="Phone No:").grid(row=6, column=0, sticky="W")
phone_no = tk.StringVar()
tk.Entry(window, textvariable=phone_no).grid(row=6, column=1)

# Create submit button
tk.Button(window, text="Submit", command=submit_order).grid(row=7, column=0, columnspan=2, pady=10)

# Start the main tkinter event loop
window.mainloop()
