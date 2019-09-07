# You-Search

from tkinter import *
import tkinter as tk
from tkinter import Text
from tkinter import ttk
import webbrowser

top = tk.Tk()
top.geometry("800x800")
top.resizable(False, False)
top.configure(bg="white")

number1 = tk.StringVar()
#Labels
top_label = tk.Label(top, text="YouSearch", font=("Gotham", 20), bg="white")
top_label.place(x=40, y=10)

creator_label = tk.Label(top, text="Developed by Pixel.", font=("Gotham", 12), bg="white")
creator_label.place(x=600, y=750)

label_en = tk.Label(top, text="Enter the video: ", anchor="nw", font=("Gotham", 18), bg="white")
label_en.place(x=22, y=354)
#Entry
query = ttk.Entry(top, textvariable=number1, width="70")
query.place(x=230, y=362)
#Buttons
btn1 = ttk.Button(top, text="Search", command=lambda: webbrowser.open("https://www.youtube.com/results?search_query=" +query.get()))  # do not make another variable to store entry.get()
btn1.place(x=685, y=360)
#----------------------------------------------#

def CambiaLingua():
    label_en.forget()
    btn1.forget()
    new_it = "Inserisci il video: "
    _new = tk.Label(top, text=new_it, font=("Gotham", 18), bg="white")
    _new.place(x=22, y=354)
    new_btn = ttk.Button(top, text="Cerca", command=lambda: webbrowser.open("https://www.youtube.com/results?search_query=" + query.get()))
    new_btn.place(x=685, y=360)

def ChangeLanguage():
    window = tk.Tk()
    window.title("YouSearch - English")
    window.geometry("800x800")
    window.configure(bg="white")
    window.resizable(False, False)

    number1 = tk.StringVar()
    #Labels
    info_en = tk.Label(window, text="This window is in English.\n For the Italian version, click on the other window.", font=("Gotham", 14), bg="white")
    info_en.place(x=300, y=0)

    info_it = tk.Label(window, text="Questa finestra è in inglese.\n Per la versione italiana, passare all'altra finestra.", font=("Gotham", 14), bg="white")
    info_it.place(x=290, y=70)
    
    top_label = tk.Label(window, text="YouSearch", font=("Gotham", 20), bg="white")
    top_label.place(x=40, y=10)

    creator_label = tk.Label(window, text="Developed by Pixel.",
                             font=("Gotham", 12), bg="white")
    creator_label.place(x=600, y=750)

    label_en = tk.Label(window, text="Enter the video: ",
                        anchor="nw", font=("Gotham", 18), bg="white")
    label_en.place(x=22, y=354)
    #Entry
    query = ttk.Entry(window, textvariable=number1, width="70")
    query.place(x=230, y=362)
    #Buttons
    btn1 = ttk.Button(window, text="Search", command=lambda: webbrowser.open(
        "https://www.youtube.com/results?search_query=" + query.get()))  # do not make another variable to store entry.get()
    btn1.place(x=685, y=360)

    def PassItalian():
        win = tk.Tk()
        win.title("YouSearch - Italiano")
        win.geometry("800x800")
        win.configure(bg="white")
        win.resizable(False, False)
        
        number1 = tk.StringVar()
        #Labels
        info_ita = tk.Label(win, text="Questa finestra è in Italiano.\n La versione inglese è già aperta in un'altra finestra.", font=("Gotham", 14), bg="white")
        info_ita.place(x=270, y=10)

        info_eng = tk.Label(win, text="This window is in Italian.\n The English version is already open in another window.", font=("Gotham", 14), bg="white")
        info_eng.place(x=250, y=80)
        
        top_label = tk.Label(win, text="YouSearch", font=("Gotham", 20), bg="white")
        top_label.place(x=40, y=10)

        creator_label = tk.Label(win, text="Developed by Pixel.", font=("Gotham", 12), bg="white")
        creator_label.place(x=600, y=750)

        label_en = tk.Label(win, text="Inserisci il video: ",
                            anchor="nw", font=("Gotham", 18), bg="white")
        label_en.place(x=22, y=354)
        #Entry
        query = ttk.Entry(win, textvariable=number1, width="70")
        query.place(x=230, y=362)
        #Buttons
        btn1 = ttk.Button(win, text="Cerca", command=lambda: webbrowser.open("https://www.youtube.com/results?search_query=" + query.get()))  # do not make another variable to store entry.get()
        btn1.place(x=685, y=360)
#-------------------------------------------------------------------------------------------------------------#
    pass_window_en = ttk.Button(window, text="Go To Italian Window", command=PassItalian)
    pass_window_en.place(x=370, y=135)
    pass_window_it = ttk.Button(window, text="Passa Alla Finestra In Italiano", command=PassItalian)
    pass_window_it.place(x=540, y=135)       #300, 0, 290, 70 
#-------------------------------------------------------------------------------------------------------------#
#change language buttons in main window

lan_en = ttk.Button(top, text="Change Language", command=ChangeLanguage)
lan_en.place(x=550, y=20)

lan_it = ttk.Button(top, text="Cambia Lingua", command=CambiaLingua)
lan_it.place(x=675, y=20)

#-----------------------------------------------------------#
top.mainloop()
#-----------------------------------------------------------#
