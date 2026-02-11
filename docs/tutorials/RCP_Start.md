# RCP Quick Start Tutorial: Uploading Data and Launching Your First Session

This tutorial walks through the complete workflow:

1. Set up your RCP account  
2. Join or create a project space  
3. Upload a small CSV file from your laptop  
4. Launch RStudio or Jupyter  
5. Read and inspect the data  
6. Properly stop your session to avoid charges  

---

# Step 1: Get an RCP Account

If you do not yet have access to RCP:

👉 Visit the [RCP Documentation Homepage](https://hbs-rcs.github.io/hbsrcp-docs/)

- Request access to the HBS Research Computing Platform (RCP).
- Log into RCP at least once before being added to a project.

Full onboarding and access documentation:  
[Getting Started with RCP](https://hbs-rcs.github.io/hbsrcp-docs/)

If you encounter issues, contact: research@hbs.edu

---

# Step 2: Join or Create a Project Space

All work in RCP happens inside a **project space**.
- If will be the project owner, request a new project space.
- If joining an existing project, ask the project owner to add you after your first login.

Project owners can:
- Add/remove team members  
- Configure available launchers  
- Monitor usage and costs  

Project management documentation:  
[Managing Projects](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/)

Once you are added to a project, you can begin uploading data and launching sessions.

---

# Step 3: Upload Your CSV File

Assume you have a file on your laptop called:

`mydata.csv`

File transfer documentation:  
[Transferring and Syncing Files](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

## For Small Files (Under 5GB)

1. Log into RCP.
2. Open your project **Workbench**.
3. Click the **Files** tab.
4. Click **Upload File**.
5. Select `mydata.csv` from your laptop.
6. Confirm the file appears in your project storage.

## For Larger or Multiple Files

- Compress files locally before upload, or  
- Use **Globus** for reliable large file transfer.

Globus documentation:  
[Using Globus with RCP](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

---

# Step 4: Choose and Start a Launcher

Launcher documentation:  
[Launchers & Sessions Guide](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

Choose the launcher based on your workflow:

| Tool      | Best For |
|-----------|----------|
| RStudio   | R analysis |
| Jupyter   | Python notebooks |
| VSCode    | General scripting, git, editing |

Available software and storage details:  
[Storage and Available Software](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

## To Start a Launcher

1. From your project Workbench, click the launcher tile.
2. Select:
   - Software image  
   - Instance size (CPU/memory)
3. Name your session.
4. Click **Create**.
5. Wait for provisioning.
6. Click **Connect** when ready.

⚠ Running sessions incur compute charges.

When finished:
- Click **Stop** (to pause)  
- Or **Terminate** (to delete permanently)

Launcher management documentation:  
[Managing Launchers and Sessions](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

---

# Step 5: Read Your CSV

Assume `mydata.csv` is in your project root.

## In R (RStudio)

```r
df <- read.csv("mydata.csv", stringsAsFactors = FALSE)
head(df)
summary(df)
```

## In Python (Jupyter or VSCode)

```python
import pandas as pd

df = pd.read_csv("mydata.csv")
print(df.head())
df.describe()
```

If you need information about available software or installing packages:  
[Software and Package Installation](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

---

# Step 6: Download Results

To download outputs:

1. Go to the **Files** tab.
2. Select your file.
3. Click **Download**.

For large downloads:
- Compress files first, or  
- Use Globus.

File transfer documentation:  
[File Transfer Guide](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

---

# Important Cost Reminder

You are charged while sessions are **running**.

To understand pricing and monitor usage:

[Billing and Pricing Documentation](https://hbs-rcs.github.io/hbsrcp-docs/billing/)

Best practice:
- Stop sessions when finished.
- Monitor project spending regularly.

---

# Quick Workflow Summary

1. Request account and log in.  
   [RCP Homepage](https://hbs-rcs.github.io/hbsrcp-docs/)

2. Join or create project space.  
   [Managing Projects](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/)

3. Upload CSV file.  
   [Transferring Files](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

4. Start launcher.  
   [Launchers & Sessions](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

5. Read data.  

6. Stop session and monitor costs.  
   [Billing Guide](https://hbs-rcs.github.io/hbsrcp-docs/billing/)

---

For help: research@hbs.edu

---

# HBS RCP Quick Start Checklist
## Uploading and Analyzing a Small CSV File

---

## Account Setup
☐ Request RCP account  
   👉 [RCP Documentation Homepage](https://hbs-rcs.github.io/hbsrcp-docs/)

☐ Log into RCP at least once  

☐ Get added to a project (or create one)  
   👉 [Managing Projects Guide](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/)

Support: research@hbs.edu

---

## Upload Your Data
☐ Log into RCP  

☐ Open your project Workbench  

☐ Click **Files** tab  

☐ Click **Upload File**  

☐ Select `mydata.csv`  

☐ Confirm file appears in project storage  

File transfer documentation:  
👉 [Transferring & Syncing Files](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

(If >5GB or many files → use Globus)

---

## Start a Launcher
☐ Choose launcher:
   - ☐ RStudio (R)
   - ☐ Jupyter (Python)
   - ☐ VSCode (general use)

Launcher documentation:  
👉 [Launchers & Sessions Guide](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

☐ Select instance size  

☐ Name session  

☐ Click **Create**  

☐ Click **Connect**

Available software details:  
👉 [Storage & Software Guide](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

⚠ Running sessions incur compute charges.

---

## Read the Data

### R
```
df <- read.csv("mydata.csv")
head(df)
```

### Python
```
import pandas as pd
df = pd.read_csv("mydata.csv")
df.head()
```

---

## When Finished
☐ Save results  

☐ Download output files (Files tab)  
   👉 [File Transfer Guide](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

☐ STOP session  

✔ Stopping avoids ongoing compute charges.

Cost and billing details:  
👉 [Billing & Pricing Guide](https://hbs-rcs.github.io/hbsrcp-docs/billing/)

---


# 🚀 HBS Research Computing Platform (RCP)
## From Laptop CSV to Live Analysis

---

# STEP 1 — Get Access
☐ Request RCP account  
   🔗 https://hbs-rcs.github.io/hbsrcp-docs/

☐ Log in at least once  

☐ Join or create a project  
   🔗 https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/

Need help? research@hbs.edu

---

# STEP 2 — Upload Your Data
File: `mydata.csv`

☐ Open Project Workbench  
☐ Go to **Files** tab  
☐ Click **Upload File**  
☐ Confirm upload  

File transfer guide:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/

Tip: Large files? Use Globus.

---

# STEP 3 — Launch Your Environment

Choose your tool:

| If you use… | Choose… |
|-------------|----------|
| R | RStudio |
| Python | Jupyter |
| Mixed / Git | VSCode |

Launcher guide:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/

☐ Select instance size  
☐ Name session  
☐ Click **Create**  
☐ Click **Connect**

Available software:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/storage_software/

⚠ Sessions cost money while running.

---

# STEP 4 — Load the Data

### R
```
df <- read.csv("mydata.csv")
head(df)
```

### Python
```
import pandas as pd
df = pd.read_csv("mydata.csv")
df.head()
```

---

# STEP 5 — Shut Down Properly

☐ Save your work  
☐ Download outputs (Files tab)  
☐ STOP session  

Billing & cost monitoring:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/billing/

✔ Stopped sessions avoid ongoing compute charges.

---

RCP Help: research@hbs.edu


