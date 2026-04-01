# Deployment Guide

## Overview

This project can be deployed using **Hugging Face Spaces** with Gradio.

The deployment script is located at:

```
intResumeDeploy.py
```

---

## Before You Start

Make sure to personalize the project:

* Update the files in the `me/` directory (CV, resume, etc.) so the agent reflects **your** background
* Set your name in `intResumeDeploy.py`:

```python
self.name = "Your Name"
```

* Check this folder:

  * If a `README.md` file exists there, **delete it**
  * (The deployment process will create a new one automatically)

---

## Step-by-Step Deployment

### 1. Create a Hugging Face Account

Go to: https://huggingface.co and sign up

---

### 2. Create an Access Token

* Click your avatar (top right) → **Settings**
* Go to **Access Tokens**
* Click **Create New Token**
* Give it **WRITE permissions**
* Save your token (you’ll need it soon)

---

### 3. Install Hugging Face CLI

In your terminal:

```bash
uv tool install "huggingface_hub[cli]"
```

Log in:

```bash
hf auth login --token YOUR_TOKEN_HERE
```

Verify login:

```bash
hf auth whoami
```

---

### 4. Save Token in `.env`

Add your token for future use:

```env
HF_TOKEN=hf_xxx
```

---

### 5. Deploy the App

Navigate to the `1_foundations` folder and run:

```bash
uv run gradio deploy
```

Follow the prompts:

* **App name:** `career_conversation`
* **Entry file:** `app.py`
* **Hardware:** `cpu-basic`
* **Secrets:** Yes
* **GitHub Actions:** No

You’ll be asked to provide:

* `OPENAI_API_KEY`
* `PUSHOVER_USER`
* `PUSHOVER_TOKEN`

---

## 🔐 About Secrets

During deployment, you’ll enter secrets as **key-value pairs**.

Example:

```
OPENAI_API_KEY
sk-xxxxxx
```

If something goes wrong, you can update secrets later:

1. Go to your Hugging Face profile
2. Open your deployed Space
3. Click **Settings** (top right)
4. Scroll to **Variables and Secrets**

---

## ✅ Deployment Complete

Once finished, your app will be live on Hugging Face Spaces.

---

## 🔁 Redeploying / Resetting

If you want to redeploy from scratch:

1. Delete your Space on Hugging Face:

   * Go to your profile → select the Space
   * Click **Settings** → scroll down → **Delete Space**

2. Delete the auto-generated file locally:

   * Remove `README.md` inside `1_foundations/`

Then run the deployment process again.

---

## 📚 Additional Resources

Gradio deployment guide:
https://www.gradio.app/guides/sharing-your-app#hosting-on-hf-spaces

---

## Notes

* If deployment behaves unexpectedly, it’s often due to:

  * Missing or incorrect secrets
  * Existing `README.md` in `1_foundations/`
* Deleting and redeploying usually resolves issues

---

## Acknowledgments

Thanks to Robert, James, Martins, Andras, and Priya for helpful deployment tips.
