---
title: "Creating and Activating a Custom Conda Environment in JupyterLab"
author: "Melissa Velez"

tags:
  - JupyterLab
  - Notebook
  - conda
  - custom
  - environment
---
# Creating and Activating a Custom Conda Environment in JupyterLab

This tutorial walks you through creating a new conda environment and making it available as a selectable kernel in JupyterLab.

---

## Step 1: Start a JupyterLab Session and Open a Terminal

Start your JupyterLab session.

<img width="219" height="137" alt="image" src="https://github.com/user-attachments/assets/d9d62a7d-35d7-4c67-b155-d7e9e2fcc715" />

Open a new **Terminal**.

<img width="293" height="135" alt="image" src="https://github.com/user-attachments/assets/f49d5579-57ea-4266-8f02-62ee3357cafe" />


---

## Step 2: Create a New Conda Environment

In the terminal, create a new conda environment. Replace `myenv` with your preferred environment name and specify your desired Python version. If prompted to proceed with installing new packages, type y.

```bash
conda create -n myenv python=3.11
```

> 💡 **Tip:** You can name your environment anything you like. Using a descriptive name helps when managing multiple environments.

---

## Step 3: Activate the Environment

```bash
conda activate myenv
```

Your terminal prompt should update to reflect the active environment, e.g., `(myenv)`.

<img width="180" height="30" alt="image" src="https://github.com/user-attachments/assets/2bbdbdb1-fd39-46aa-9a54-87a6347a81f3" />


---

## Step 4: Install `ipykernel` and Other Packages

With the environment active, install the `ipykernel` package (required) along with any other packages needed in your conda environment:

```bash
pip install ipykernel numpy pandas matplotlib
```

> 💡 **Tip:** Whenever you need to install additional packages into this environment in the future, open a **Terminal** in JupyterLab, activate the environment with `conda activate myenv`, and then run your `pip install` or `conda install` command.

---

## Step 5: Register the Environment as a Jupyter Kernel

Run the following command to make your conda environment visible as a selectable kernel in JupyterLab:

```bash
python -m ipykernel install --user --name myenv --display-name "Python(myenv)"
```

| Flag | Description |
|------|-------------|
| `--user` | Installs the kernel for the current user only |
| `--name` | Internal name used to identify the kernel |
| `--display-name` | The name shown in the JupyterLab UI |

---

## Step 6: Select Your Kernel and Start Working

After a moment, open a new tab in JupyterLab. In the **Notebook** section of the Launcher, you should now see your new environment listed as a kernel option alongside the default:

- `Python 3 (ipykernel)` *(default)*
- `Python(myenv)` ✅ *(your new environment)*

**To start a new notebook using your environment**, click the Python(myenv) icon in the Launcher.

**To switch the kernel in an existing notebook**, click the kernel name in the **top right corner** (next to the small bug icon) and select **Python(myenv)** from the dropdown.

<img width="584" height="297" alt="image" src="https://github.com/user-attachments/assets/7014146a-f45b-4d20-afe6-220d5409765c" />

---

## Summary

```
conda create -n myenv python=3.11
conda activate myenv
pip install ipykernel numpy pandas matplotlib
python -m ipykernel install --user --name myenv --display-name "Python(myenv)"
```

Once registered, your environment will persist as a kernel option in JupyterLab until you explicitly remove it.
