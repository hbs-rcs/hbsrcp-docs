---
title: "RCP Quick Start Tutorial"
author: "Melissa Velez"

tags:
  - quick start
  - project space
  - upload data
  - launch session
  - transfer data
---

# RCP Quick Start Tutorial: Uploading Data and Launching Your First Session

This tutorial walks through the complete workflow:

1. Set up your RCP account  
2. Create or join a project space  
3. Upload a small CSV file from your laptop  
4. Launch RStudio  
5. Read and inspect the data  
6. Properly stop your session to avoid charges  

---

# Step 1: Get an RCP Account

If you do not yet have access to RCP:

👉 Check out our [Quick Start guide](https://hbs-rcs.github.io/hbsrcp-docs/#quick-start)

- Request access to the HBS Research Computing Platform (RCP). You will receive an email once your account has been provisioned.
- Log into RCP at least once before requesting or being added to a project.

Full onboarding and access documentation:  
[Getting Started with RCP](https://hbs-rcs.github.io/hbsrcp-docs)

If you encounter issues, contact: [research@hbs.edu](mailto:research@hbs.edu)

---

# Step 2: Create or Join a Project Space

All work in RCP happens inside a **project space**.
- If you will be the project owner, [request a new project space](https://secure.hbs.edu/accountManagement/secure/research-computing-platform/projectspace/new).
- If joining an existing project, ask the project owner to add you after your first login by reaching out to [research@hbs.edu](mailto:research@hbs.edu).

Project owners can:
- Authorize adding/removing team members  
- [Configure available launchers](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/#configure-services) 
- [Monitor usage and costs](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/#view-costs)

Project management documentation:  
[Managing Projects](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/)

Once your project space has been created or you are added to a project, you can begin uploading data and launching sessions.

---

# Step 3: Upload Your CSV File

Assume you have a file on your laptop called:

`mydata.csv`

File transfer documentation:  
[Transferring and Syncing Files](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

## For Small Files (Under 5GB)

1. Log into RCP.
2. Click on your project.
3. Click the **Files** tab.
4. Click **Upload File**.
5. Select `mydata.csv` from your laptop.
6. Confirm the file appears in your project storage.

## For Larger or Multiple Files

- [Compress](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/) files locally before upload, or  
- Use [Globus](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/#transferring-files) for reliable large file transfer.

---

# Step 4: Choose and Start a Launcher

## To Start a Launcher

1. Click on the project Workbench. For this tutorial, we will use RStudio. Click on the RStudio launcher. 
2. Name your session.
3. Select the instance size (CPU/GPU/RAM) appropriate for your work.
4. Click **Provision**.
5. Wait for provisioning. Note that this can take 5-10 minutes.
6. Click **Connect** when ready.

⚠ Running sessions incur compute charges.

When finished:
- Click **Stop** (to pause)  
- Or **Terminate** (to delete permanently)

Launcher management documentation:  
[Managing Launchers and Sessions](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

Available software and storage details:  
[Storage and Available Software](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

---

# Step 5: Read Your CSV

Files you have uploaded can be found in your project folder. This typically takes the form of "/home/ec2-user/studies/YourProjectName." Assume `mydata.csv` is in this project folder.

## In R (RStudio)

```r
df <- read.csv("/home/ec2-user/studies/YourProjectName/mydata.csv", stringsAsFactors = FALSE)
head(df)
summary(df)
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
- [Compress](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/) files first, or  
- Use Globus [**Globus**](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/#transferring-files).

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
   [RCP Homepage](https://hbs-rcs.github.io/hbsrcp-docs/#quick-start)

2. Create or join a project space.  
   [Managing Projects](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/)

3. Upload CSV file.  
   [Transferring Files](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

4. Start launcher.  
   [Launchers & Sessions](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

5. Read data.  

6. Stop session and monitor costs.  
   [Billing Guide](https://hbs-rcs.github.io/hbsrcp-docs/billing/)

---

For help: [research@hbs.edu](mailto:research@hbs.edu)


