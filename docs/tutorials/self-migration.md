# Self-Migration from the HBSGrid to the RCP

This guide walks you through moving an existing HBSGrid project to the HBS Research Computing Platform (RCP).

## Step 1: Get access to the RCP

Request an RCP account and log in to activate your account.

2. Request the RCP project that will replace your HBSGrid project.

[Get started with the RCP](https://hbs-rcs.github.io/hbsrcp-docs/#quick-start)

---
##  Step 2: Check your data security requirements

If your HBSGrid project space contains **Level 3 or Level 4 data**, you must update your **DAT record** to include the RCP as a storage location before moving the data.

[How to update your DAT record](https://hbs-rcs.github.io/hbsrcp-docs/media/RCP%20Migration.pdf)

The RCP supports research data at Levels 1–4.

---

## Step 3: Move your data

For small amounts of data, you can upload files through the RCP **Files** interface.

For large datasets or many files, use **Globus**.

[Transfer files to the RCP](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

Contact [RCS](mailto:research@hbs.edu) for guidance on migrating MariaDB databases.

---

## Step 4: Recreate your computing environment

Assign launchers, configurations, and services to your project space.

[Manage your project](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

Launch the RCP tools you need and recreate your environments:

- JupyterLab
- RStudio
- Stata
- Spyder
- VS Code
- MATLAB

[Launching sessions](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

[Recreating your environments](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/#available-software-and-analysis-tools)

---

## Step 5: Recreate your batch jobs (if applicable)

If your HBSGrid project uses the scheduler for batch jobs, review your job scripts carefully.

HBSGrid uses **LSF**; RCP uses **SLURM/PCS**, so existing submission scripts will need to be updated.

[Learn about batch jobs]([https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/#aws-parallel-computing-service-pcs))

If you do **not need a job scheduler** and your primary aim is to run background jobs, you can run these inside launchers.

[Background jobs in launchers](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/#running-background-jobs)

---

## Step 6: Add your collaborators

1. Ensure everyone who needs access has an RCP account and has logged in once to activate the account
2. Email [RCS](mailto:research@hbs.edu) to add collaborators to your space.

---

## Step 8: Test before you retire the HBSGrid Project Space

Before moving off the HBSGrid, verify that:

- [ ] Your data is complete
- [ ] Your code runs
- [ ] Your jobs run successfully
- [ ] Your collaborators have access

Once everything is working, please contact [RCS](mailto:research@hbs.edu) so that we can archive the HBSGrid project.

---

## Need help?

RCS can help with migration questions.

Contact **Research Computing Services** at [research@hbs.edu](mailto:research@hbs.edu).
