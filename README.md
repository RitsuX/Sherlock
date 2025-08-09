#  Sherlock OSINT Tool Guide  
*A step-by-step walkthrough for installing, using, and troubleshooting Sherlock while maintaining privacy.*

---

## What is OSINT?

**OSINT** stands for **Open-Source Intelligence**, which means collecting information from publicly available sources online, such as websites, social media, and forums.

Sherlock is an OSINT tool used to find usernames across many social networks by gathering publicly accessible data.

---

## **1. Installation**

### **Prerequisites**
- Kali Linux (or any Linux/macOS with Python 3.6+)
- `git` and `pip` installed

### **Steps**
```bash
# Clone the repository
git clone https://github.com/sherlock-project/sherlock.git
cd sherlock

# Set up a virtual environment (to avoid conflicts)
python3 -m venv sherlock-venv
source sherlock-venv/bin/activate

# Install dependencies
pip install -e .
````

**Fix for Kali Linux Errors**:
If you see `externally-managed-environment`, use:

```bash
pip install --break-system-packages -e .  # Not recommended for stable systems
```

---

## **2. Basic Usage**

### **Search for a Username**

```bash
python3 sherlock_project/sherlock.py "username"
```

For names with spaces, use quotes:

```bash
python3 sherlock_project/sherlock.py "John Doe"
```

### **Search on Specific Sites**

```bash
python3 sherlock_project/sherlock.py --site Instagram,GitHub username
```
## Output File

The output from running Sherlock is saved in the file [`output.txt`](output.txt) located in the root folder of this repository.


## **4. Common Issues & Fixes**

| Error                            | Solution                                        |
| -------------------------------- | ----------------------------------------------- |
| `ModuleNotFoundError`            | Run `pip install requests httpx beautifulsoup4` |
| `externally-managed-environment` | Use `venv` or `pipx` (Kali Linux)               |
| `sherlock.py not found`          | Run from `sherlock_project/` directory          |

---

