# Migrating from HBSGrid to the RCP

This guide walks you through moving an existing HBSGrid project to the HBS Research Computing Platform (RCP).

## Step 1: Get access to the RCP

Request an RCP account and log in.

Then create or request the RCP project that will replace your HBSGrid project.

[Get started with the RCP](https://hbs-rcs.github.io/hbsrcp-docs/)

---
##  Step 2: Check your data security requirements

If your HBSGrid project space contains **Level 3 or Level 4 data**, you must update your **DAT record** to include the RCP as a storage location before moving the data.

[How to update your DAT record](PLACEHOLDER)

The RCP supports research data at Levels 1–4.

---

## Step 3: Move your data

For small amounts of data, you can upload files through the RCP **Files** interface.

For large datasets or many files, use **Globus**.

A typical migration looks like:

**HBSGrid project space → Globus → RCP project storage**

!!! important
    Keep the HBSGrid copy until you have verified that your data transferred successfully.

[Transfer files to the RCP](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

---

## Step 4: Recreate your computing environment

Start the RCP tools you need, such as:

- JupyterLab
- RStudio
- Stata
- Spyder
- VS Code
- MATLAB

Reinstall project-specific Python or R packages and bring over any environment files you use, such as:

```text
requirements.txt
environment.yml
renv.lock
```

[See RCP software and storage](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

---

## Step 5: Recreate your jobs

If your HBSGrid project uses batch jobs, review your job scripts carefully.

HBSGrid uses **LSF**; RCP uses **SLURM/PCS**, so existing submission scripts will need to be updated.

[Learn about RCP compute and sessions](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

---

## Step 6: Move your code and services

Clone or sync your Git repositories in the RCP.

For databases or other specialized services, review the RCP options or contact RCS for help with the migration.

[Learn about file transfer and Git](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

---

## Step 7: Add your collaborators

Make sure everyone who needs access:

1. Has an RCP account
2. Has logged in at least once
3. Has been added to the project
4. Can access the files and tools they need

[Manage your RCP project](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/)

---

## Step 8: Test before you retire HBSGrid

Before moving off the HBSGrid, verify that:

- [ ] Your data is complete
- [ ] Your code runs
- [ ] Your required packages are installed
- [ ] Your jobs run successfully
- [ ] Your collaborators have access
- [ ] Any required compliance steps are complete

Once everything is working, you can retire or archive the HBSGrid project.

---

## Need help?

RCS can help with migration questions.

Contact **Research Computing Services** at [research@hbs.edu](mailto:research@hbs.edu).
