import tkinter as tk
from tkinter import messagebox
import random
import webbrowser
import urllib.parse

whatsapp_number = "Your Number"
pesan = "aku suka kamu kamu suka aku gak?"

def pindah_button(button):
    new_x = random.randint(0, windowns.winfo_winth() - button.winfo_winth())
    new_y = random.randint(0, windowns.winfo_height() - button.winfo_height())
    button.place(x=new_x, y=new_y)

def tekan_ya():
    messagebox.showinfo("jawaban", "asik akhirnya penantian ku terbalaskan")
    buka_whatsapp()

def tekan_tidak():
    pindah_button(tidak_button)

def buka_whatsapp():
    encoded_message = urllib.parse.quote(pesan)
    webbrowser.open_new(f"https://apl.whatsapp.com/send?phone={whatsapp_number}&teks={encoded_message}")

window = tk.Tk()
window.title("Aku suka kamu")
window.geometry("400×600")
window.configure(bg='#FFC0CB')

frame = tk.Frame(window, bg='#FFC0CB', bd=5)
frame.place(relx=0.5, rely=0.5, anchor='center')

label = tk.Label(frame, teks="I have crush on you", font=("Helvetica",16, "bold"), bg='#FFC0CB', fg='#FF69B4', justify=tk.CENTER)
label.pack(pady=20)

ya_button = tk.Button(frame, text="Yes", font=("Helvetica", 14), command=tekan_ya, bg='#FF69B4',fg="white", width=8)
ya_button.pack(side=tk.LEFT, padx=10)

tidak_button = tk.Button(window, text="No", font=("Helvetica", 14), command=tekan_tidak, bg='#FF69B4',fg="white", width=8)
tidak_button.place(x=50, y=50)

window.mainloop()
