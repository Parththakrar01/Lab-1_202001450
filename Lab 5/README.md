# SE_Lab5_202001450

IT-314 Assignment 5


Name: Thakrar Parth N.

Student ID: 202001450

## Static Analysis of code using Static analysis tools

Github repositury used:

https://github.com/IncrediblePro/Hacktoberfest_2022

File analysed using Static Analysis tools:

1) AlarmClock.py
2) DigitalClock.py

## AlarmClock.py errorneous code

```python
from tkinter import *
import datetime
import time
import winsound
from threading import *
find = Tk()
find.geometry("400x400")
def Threading():
    t1=Thread(target=alarm)
    t1.start()
 
def alarm():
    while True:
        set_alarm_time = f"{hur.get()}:{min.get()}:{sec.get()}"
        time.sleep(1)
        current_time = datetime.datetime.now().strftime("%H:%M:%S")
        print(current_time,set_alarm_time)
 
        if current_time == set_alarm_time:
            print("Good Morning !!!")
Label(find,text="Alarm Clock",font=("Helvetica 20 bold"),fg="blue").pack(pady=10)
Label(find,text="Set Time",font=("Helvetica 15 bold")).pack()
 
frame = Frame(find)
frame.pack()
 
hur = StringVar(find)
hurs = ('00', '01', '02', '03', '04', '05', '06', '07','08', '09', '10', '11', '12', '13', '14', '15','16', '17', '18', '19', '20', '21', '22', '23', '24')
hur.set(hurs[0])
 
hrs = OptionMenu(frame, hur, *hurs)
hrs.pack(side=LEFT)
 
min = StringVar(find)
mins = ('00', '01', '02', '03', '04', '05', '06', '07','08', '09', '10', '11', '12', '13', '14', '15','16', '17', '18', '19', '20', '21', '22', '23','24', '25', '26', '27', '28', '29', '30', '31','32', '33', '34', '35', '36', '37', '38', '39','40', '41', '42', '43', '44', '45', '46', '47','48', '49', '50', '51', '52', '53', '54', '55','56', '57', '58', '59', '60')
min.set(mins[0])
 
mins = OptionMenu(frame, min, *mins)
mins.pack(side=LEFT)
 
sec = StringVar(find)
secs = ('00', '01', '02', '03', '04', '05', '06', '07','08', '09', '10', '11', '12', '13', '14', '15','16', '17', '18', '19', '20', '21', '22', '23','24', '25', '26', '27', '28', '29', '30', '31','32', '33', '34', '35', '36', '37', '38', '39','40', '41', '42', '43', '44', '45', '46', '47','48', '49', '50', '51', '52', '53', '54', '55','56', '57', '58', '59', '60')
sec.set(secs[0])
 
secs = OptionMenu(frame, sec, *secs)
secs.pack(side=LEFT)
 
Button(find,text="Set Alarm",font=("Helvetica 15"),command=Threading).pack(pady=20)
find.mainloop()
```

## AlarmClock.py error snippet using mypy tool

AlarmClock.py:5: error: Incompatible import of "Event" (imported name has type "Type[threading.Event]", local name has type "Type[tkinter.Event[Any]]")  [assignment]

AlarmClock.py:38: error: Incompatible types in assignment (expression has type "OptionMenu", variable has type "Tuple[str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str]")  [assignment]

AlarmClock.py:39: error: "Tuple[str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str]" has no attribute "pack"  [attr-defined]

AlarmClock.py:45: error: Incompatible types in assignment (expression has type "OptionMenu", variable has type "Tuple[str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str]")  [assignment]

AlarmClock.py:46: error: "Tuple[str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str, str]" has no attribute "pack"  [attr-defined]

Found 5 errors in 1 file (checked 1 source file)

## DigitalClock.py errorneous code

```python
# importing whole module
from tkinter import *
from tkinter.ttk import *

# importing strftime function to
# retrieve system's time
from time import strftime

# creating tkinter window
root = Tk()
root.title('Clock')

# This function is used to
# display time on the label
def time():
	string = strftime('%H:%M:%S %p')
	lbl.config(text = string)
	lbl.after(1000, time)

# Styling the label widget so that clock
# will look more attractive
lbl = Label(root, font = ('calibri', 40, 'bold'),
			background = 'purple',
			foreground = 'white')

# Placing clock at the centre
# of the tkinter window
lbl.pack(anchor = 'center')
time()

mainloop()
```

## DigitalClock.py error snippet using pylint tool

DigitalClock.py:16:0: W0311: Bad indentation. Found 1 spaces, expected 4 (bad-indentation)

DigitalClock.py:17:0: W0311: Bad indentation. Found 1 spaces, expected 4 (bad-indentation)

DigitalClock.py:18:0: W0311: Bad indentation. Found 1 spaces, expected 4 (bad-indentation)

DigitalClock.py:31:0: C0304: Final newline missing (missing-final-newline)

DigitalClock.py:1:0: C0114: Missing module docstring (missing-module-docstring)

DigitalClock.py:1:0: C0103: Module name "DigitalClock" doesn't conform to snake_case naming style (invalid-name)

DigitalClock.py:2:0: W0401: Wildcard import tkinter (wildcard-import)

DigitalClock.py:3:0: W0401: Wildcard import tkinter.ttk (wildcard-import)

DigitalClock.py:15:0: C0116: Missing function or method docstring (missing-function-docstring)

DigitalClock.py:2:0: W0614: Unused import(s) enum, sys, types, TclError, re, wantobjects, TkVersion, TclVersion, READABLE, WRITABLE, EXCEPTION, EventType, Event, NoDefaultRoot, Variable, StringVar, IntVar, DoubleVar, BooleanVar, getint, getdouble, getboolean, Misc, CallWrapper, XView, YView, Wm, Tcl, Pack, Place, Grid, BaseWidget, Widget, Toplevel, Button, Canvas, Checkbutton, Entry, Frame, Listbox, Menu, Menubutton, Message, Radiobutton, Scale, Scrollbar, Text, OptionMenu, Image, PhotoImage, BitmapImage, image_names, image_types, Spinbox, LabelFrame, PanedWindow, NO, FALSE, OFF, YES, TRUE, ON, N, S, W, E, NW, SW, NE, SE, NS, EW, NSEW, CENTER, NONE, X, Y, BOTH, LEFT, TOP, RIGHT, BOTTOM, RAISED, SUNKEN, FLAT, RIDGE, GROOVE, SOLID, HORIZONTAL, VERTICAL, NUMERIC, CHAR, WORD, BASELINE, INSIDE, OUTSIDE, SEL, SEL_FIRST, SEL_LAST, END, INSERT, CURRENT, ANCHOR, ALL, NORMAL, DISABLED, ACTIVE, HIDDEN, CASCADE, CHECKBUTTON, COMMAND, RADIOBUTTON, SEPARATOR, SINGLE, BROWSE, MULTIPLE, EXTENDED, DOTBOX, UNDERLINE, PIESLICE, CHORD, ARC, FIRST, LAST, BUTT, PROJECTING, ROUND, BEVEL, MITER, MOVETO, SCROLL, UNITS and PAGES from wildcard import of tkinter (unused-wildcard-import)

DigitalClock.py:3:0: W0614: Unused import(s) tkinter, tclobjs_to_py, setup_master, Style, Combobox, Labelframe, Notebook, Panedwindow, Progressbar, Separator, Sizegrip, Treeview and LabeledScale from wildcard import of tkinter.ttk (unused-wildcard-import)

-----------------------------------
Your code has been rated at 1.54/10
