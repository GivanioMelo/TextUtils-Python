# TextUtils
simple console helper module for noob python developers (like me)

with this module you can build cool interfaces to your basic console applications, or even build nice little games with it...
![image](https://github.com/user-attachments/assets/c62e94af-da5d-424d-b194-54056a32331f)
![image](https://github.com/user-attachments/assets/1e3f14e1-2b38-4c49-8eb4-a61796eea6ba)


## Printing in colors
This module has a lot of premade functions you can use to print in colors... the general use of those print functions are identical to the basic use of the standard print function.
```python
print("Hello World")
printBlack("Hello World")
printBlue("Hello World")
printYellow("Hello World")
printRed("Hello World")
printGreen("Hello World")
printBrightBlue("Hello World")
printBrightCyan("Hello World")
printBrightGreen("Hello World")
printBrightMagenta("Hello World")
```
![image](https://github.com/user-attachments/assets/e7c17dfa-88f2-4755-ba39-f9dd4590d21e)

if you want more freedom, you can compose your own color schemes using printColored function:
```python
printColored("Hello World", color= BACKGROUND_YELLOW + BLUE)
```
![image](https://github.com/user-attachments/assets/b357f7da-3959-4f3e-a22d-258d1e6821a7)

## Clear the screen
I know you probably know how to import os and use system("cls")... but i already did it for you....
just call clearScreen() and there is no more... well... anything... in the screen...

## Choosing where to print
This function was named after the classic goToXY Pascal function, (yes, i'm that old...) and it basically moves the cursor in the console window.
The cordinate system starts at (1,1) (left, top) and, by default, ends at (120,30) (right, bottom) 120 columns and 30 rows, for a default console.
but you can resize your console at will.

```python
from TextUtils import *
import random

clearScreen()
for i in range(100):
    x = random.randint(1,120)
    y = random.randint(1,30)
    gotoxy(x,y)
    print("*")
input()
```
![image](https://github.com/user-attachments/assets/112b50fa-657d-4282-ab2b-fe2548f74751)

>>> You can also use it to choose where the user can input data...

## Drawing Boxes
The box drawing functions can be used to made really cool interfaces in your console...
The cordinate system starts at (1,1) (left, top) and, by default, ends at (120,30) (right, bottom) 120 columns and 30 rows, for a default console.
but you can resize your console at will.

The parameters are x, y, width, height, and optionally color... (default is white)

```python
#default box drawing function...
drawBox(1,1,10,10,color=YELLOW , charSet=SIMPLE_BORDER_CHARSET)

#specialized functions
drawSimpleBorderBox(12,1,10,10,color=RED)
drawHeavyBorderBox(23,1,10,10,color=GREEN)
drawBroadBorderBox(34,1,10,10,color=BLUE)
drawRoundBorderBox(45,1,10,10,color=MAGENTA)
drawDoubleBorderBox(56,1,10,10,color=CYAN)
```

![image](https://github.com/user-attachments/assets/73d5af27-2e4b-4b2b-b33d-d2f2551dfb67)


## Creating Title Bar at the top of the console screen.
```python
printTitleBar("Title Bar")
```
![image](https://github.com/user-attachments/assets/6adbc923-8662-43a3-9283-d2b41533d92b)

You can use optional parameters boxCollor and textColor to create different results
```python
printTitleBar("Title Bar", boxColor=GREEN, textColor=YELLOW)
```
![image](https://github.com/user-attachments/assets/0fe103c4-6df4-48fc-b81a-2933b80b89f2)

Other alternative versions are:
```python
printTitleBarBroadBorder("Title Bar", boxColor=GREEN, textColor=YELLOW)
printTitleBarDoubleBorder("Title Bar", boxColor=GREEN, textColor=YELLOW)
printTitleBarHeavyBorder("Title Bar", boxColor=GREEN, textColor=YELLOW)
printTitleBarRoundBorder("Title Bar", boxColor=GREEN, textColor=YELLOW)
```
![image](https://github.com/user-attachments/assets/ce6597a3-b3cf-42dd-999d-44ff62adaa4c)
![image](https://github.com/user-attachments/assets/d0152f1b-72e5-43e0-882f-e628a50c9e00)
![image](https://github.com/user-attachments/assets/14b3fd93-5686-4e3f-b01b-75d2ae4fe12b)
![image](https://github.com/user-attachments/assets/616c1e7c-4055-4cf0-81d0-b474d6da18d4)

## Table Funcionality

You can create symple tables providing the data in lists with or without headers

```python
# data = [
# 	["Name", "Age", "City"],
# 	["Alice", 25, "New York"],
# 	["Bob", 30, "Los Angeles"],
# 	["Charlie", 35, "Chicago"],
# 	["Diana", 28, "Houston"]
# ]
# TextUtils.drawTable(1,1,15,data)
```
<img width="584" height="277" alt="Captura de tela 2026-03-04 111307" src="https://github.com/user-attachments/assets/d2a3e701-5176-41e3-b05f-d66b23dd388a" />

```python
headers = ["Name", "Age", "City","Occupation","income (USD)"]
data = [
	["Alice", 25, "New York","Engineer", "75000.50"],
	["Bob", 30, "Los Angeles","Designer", "65000.75"],
	["Charlie", 35, "Chicago","Manager", "80000.00"],
	["Diana", 28, "Houston","Developer", "70000.25"]
]

alignments = [TextUtils.LEFT, TextUtils.CENTER, TextUtils.LEFT, TextUtils.LEFT, TextUtils.RIGHT]

TextUtils.clearScreen()
TextUtils.drawTableWithHeaders(1,1,15,headers,data,gridColor=TextUtils.CYAN, headerColor=TextUtils.BOLD_CYAN, alignments=alignments)
input()
```
<img width="1141" height="288" alt="Captura de tela 2026-03-04 110817" src="https://github.com/user-attachments/assets/e8d56cdd-fe9d-4666-9f05-36bdf50e2d88" />

