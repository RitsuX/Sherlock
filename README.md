#  Sherlock OSINT Tool Guide  
*A step-by-step walkthrough for installing, using, and troubleshooting Sherlock while maintaining privacy.*

---

## **1. Installation**

### **Prerequisites**
- Kali Linux (or any Linux/macOS with Python 3.6+)
- `git` and `pip` installed

### **Correct Installation Process**

```bash
# Clone the repository
git clone https://github.com/sherlock-project/sherlock.git
cd sherlock

# Set up virtual environment
python3 -m venv sherlock-venv
source sherlock-venv/bin/activate

# Install dependencies (from pyproject.toml)
pip install -e .
````

---

### **Important Notes**

1. **Directory Structure Change**

   * The main script is now in `sherlock_project/` subdirectory
   * Always run commands from there after installation:

     ```bash
     cd sherlock_project
     python3 sherlock.py username
     ```

2. **Common Mistakes to Avoid**

   * ❌ Don’t run directly from the root `sherlock/` directory (will get *file not found* errors).
   * ✅ Always activate your virtual environment in each new session:

     ```bash
     source ../sherlock-venv/bin/activate
     ```

3. **Alternative Installation**
   If you prefer manual dependency management:

   ```bash
   pip install requests httpx beautifulsoup4
   ```

4. **Fix for Kali Linux Errors**
   If you see `externally-managed-environment`, use:

   ```bash
   pip install --break-system-packages -e .  # Not recommended for stable systems
   ```

---

## **2. Basic Usage**

### **Search for a Username**

```bash
cd sherlock_project
python3 sherlock.py "username"
```

For names with spaces, use quotes:

```bash
python3 sherlock.py "John Doe"
```

### **Search on Specific Sites**

```bash
python3 sherlock.py --site Instagram,GitHub username
```

---

## **Output File**

The results of the Sherlock scan are saved to [`output.txt`](output.txt).


---

## **4. Common Issues & Fixes**

| Error                            | Solution                                        |
| -------------------------------- | ----------------------------------------------- |
| `ModuleNotFoundError`            | Run `pip install requests httpx beautifulsoup4` |
| `externally-managed-environment` | Use `venv` or `pipx` (Kali Linux)               |
| `sherlock.py not found`          | Run from `sherlock_project/` directory          |

---

## **5. Ethical Notes**

*  **Legal Use Only**: Always get permission before scanning.
*  **Avoid Doxxing**: Never share identifiable info in screenshots.
*  **Compliance**: Follow GitHub’s [Terms of Service](https://docs.github.com/en/site-policy/github-terms/github-terms-of-service).

