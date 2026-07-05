# Creating and Activating a Custom Conda Environment as a Jupyter Kernel

This tutorial walks you through creating a new conda environment and making it available as a selectable kernel in JupyterLab.

---

## Step 1: Start a JupyterLab Session and Open a Terminal

Start your JupyterLab session (note: this assumes you have already launched JupyterLab).

<img width="219" height="137" alt="image" src="https://github.com/user-attachments/assets/d9d62a7d-35d7-4c67-b155-d7e9e2fcc715" />

Open a new **Terminal**.

<img width="293" height="135" alt="image" src="https://github.com/user-attachments/assets/f49d5579-57ea-4266-8f02-62ee3357cafe" />


---

## Step 2: Create a New Conda Environment

In the terminal, create a new conda environment. Replace `myenv` with your preferred environment name and specify your desired Python version. If prompted to proceed with installing new packages, type Y.

```bash
conda create -n myenv python=3.11
```

> 💡 **Tip:** You can name your environment anything you like. Using a descriptive name helps when managing multiple environments.

---

## Step 3: Activate the Environment

```bash
conda activate myenv
```

Your terminal prompt should update to reflect the active environment, e.g. `(myenv)`.

---

## Step 4: Install `ipykernel`

With the environment active, install the `ipykernel` package:

```bash
pip install ipykernel
```

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

## Step 6: Verify the Kernel Appears in JupyterLab

After a moment, open a new tab in JupyterLab. Under the **Notebook** section of the Launcher, you should now see two options:

- `Python 3 (ipykernel)` *(default)*
- `Python(myenv)` ✅ *(your new environment)*

> 📷 *Screenshot placeholder — JupyterLab Launcher showing both kernel options*

---

## Step 7: Start Using Your New Kernel

You have two options:

### Option A — Start a new notebook with your kernel
Click the **Python(myenv)** icon in the Launcher to open a new notebook that uses your custom environment.

> 📷 *Screenshot placeholder — Clicking the Python(myenv) kernel in the Launcher*

### Option B — Switch the kernel in an existing notebook
In an open notebook, click the kernel name displayed in the **top right corner** (next to the small bug 🐛 icon). Select **Python(myenv)** from the dropdown.

> 📷 *Screenshot placeholder — Kernel switcher dropdown in the top right of a notebook*

---

## Summary

```
conda create -n myenv python=3.11
conda activate myenv
pip install ipykernel
python -m ipykernel install --user --name myenv --display-name "Python(myenv)"
```

Once registered, your environment will persist as a kernel option in JupyterLab until you explicitly remove it.
