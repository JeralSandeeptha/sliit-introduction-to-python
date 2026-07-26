# Virtul Environments

A virtual environment in Python is a separate, isolated workspace where you can install and manage Python packages without affecting other projects or the system-wide Python installation.

What a virtual environment does

- Has its own Python interpreter
- Has its own site-packages directory
- Allows installing packages only for that project
- Prevents version conflicts between projects

<br />

## Create a virtual env

- Create it

```bash
python -m venv venv
```

- Activate it

```bash
# for MacOS
source venv/bin/activate

# for Windows
venv\Scripts\activate.bat
```

<br />

## Requirements.txt

Why use requirements.txt?

- ✅ Keeps track of project dependencies
- ✅ Makes projects easy to share and deploy
- ✅ Ensures consistent versions across systems
- ✅ Commonly required for GitHub, servers, and cloud platforms

```bash
# Without versions
requests
numpy
pandas
flask

# With versions
requests==2.31.0
numpy>=1.24
pandas<3.0
```

Run this command in the folder containing requirements.txt:

```bash
pip install -r requirements.txt
```
