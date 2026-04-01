# Setup Guide

Follow these steps to get the repository up and running on your machine.

---

## Part 1 — Clone the Repository

Open your command prompt (or terminal) and navigate to the folder where you want to store the project.

Run:

```bash
git clone https://github.com/zevaz13/AgenticAIprojects.git
```

This will download the repository to your computer.

---

## Part 2 — Install an IDE (Cursor Recommended)

I used **Cursor** for development, but any IDE (like VS Code) should work.

### Install Cursor

1. Go to: https://www.cursor.com/
2. Click **Sign In** → then **Sign Up** to create an account
3. Download and install Cursor

---

### Open the Project in Cursor

1. Launch Cursor
2. Go to **File → New Window**
3. Click **Open Project**
4. Select the folder you just cloned
5. Click **Open**

You may be prompted to install recommended extensions (Python, Jupyter).
👉 If so, click **Yes**.

Once opened, you should see the project files in the Explorer panel on the left.

---

## Part 3 — Install Dependencies (uv)

This project uses **uv** as a package manager (fast and simple).

### Install uv

Follow the official instructions:
https://docs.astral.sh/uv/getting-started/installation/

👉 Recommended: use the **Standalone Installer** (top option on the page)

---

### Set Up the Environment

1. Open a terminal inside Cursor:

   * Go to **View → Terminal**

2. (Optional) Check your current directory:

```bash
pwd
```

3. Update uv:

```bash
uv self update
```

4. Install all dependencies:

```bash
uv sync
```

That’s it ✅

* This will automatically install Python (if needed)
* It will also install all required packages for the project

---

## Notes

* Some projects may require additional setup (e.g., API keys in a `.env` file)
* Check each project’s README for project-specific instructions

---

## You're Ready 🚀

You can now explore and run the projects in this repository.
