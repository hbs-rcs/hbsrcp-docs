---
title: "Copying RCP Files to Dropbox with rclonel"
author: "Melissa Velez"

tags:
  - rclone
  - sync data
  - copy data
  - transfer data
  - upload data
---

# Copying RCP Files to Dropbox with rclone

rclone is a command-line tool that can be used to copy files between your RCP project space and Dropbox. This tutorial walks through configuring a Dropbox connection and copying files from the RCP to Dropbox.

## 1. Open rclone in the Utility Launcher

Start and connect to the [Utility Launcher](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/#utility-launcher) inside your RCP project space. Once connected, open a **Terminal**.

## 2. Configure rclone to connect to Dropbox

In the Terminal, type:

```bash
rclone config
```

### Create a new remote

Indicate that you would like to create a **new remote** and give it a name.

You will use this name later when copying files between the RCP and Dropbox.

<img width="878" height="298" alt="image" src="https://github.com/user-attachments/assets/18ea91d4-3252-4672-9200-82eb950fb98a" />

### Select Dropbox

Select **Dropbox** as your storage provider.

<img width="889" height="513" alt="image" src="https://github.com/user-attachments/assets/52d02873-d349-4f86-8eaa-f986f4271ea4" />

<br></br>
When prompted for `client_id` and `client_secret`, leave both fields empty and press **Enter** to accept the defaults.

<img width="628" height="350" alt="image" src="https://github.com/user-attachments/assets/b5450e87-d069-4254-a485-e7b06af33dff" />

<br></br>
When asked whether you would like to edit the advanced configuration, select **No**.

<img width="367" height="142" alt="image" src="https://github.com/user-attachments/assets/259e8fec-06ac-4c7f-8f94-1248864d9f61" />


## 3. Authenticate with Dropbox

The next steps depend on how you normally authenticate to Dropbox.

> **Important:** If you use passwordless authentication—such as a passkey, fingerprint, Face ID, or another authentication method tied to your local device—you will not be able to complete that authentication from the browser running inside the RCP. Follow the **Passwordless authentication** instructions below instead.

### If you do not use passwordless authentication

When rclone asks whether you would like to use a web browser to automatically authenticate the remote, select **Yes**.

<img width="876" height="256" alt="image" src="https://github.com/user-attachments/assets/75d7f00d-a4be-4df7-9cf7-a6857e39b423" />

<img width="891" height="295" alt="image" src="https://github.com/user-attachments/assets/8248ce61-ab8c-41e4-8ad9-37bb2dfaf51a" />
<br></br>
A browser will open inside the Utility Launcher.
<img width="975" height="616" alt="image" src="https://github.com/user-attachments/assets/2ee5598f-d12e-4199-9ff8-d9ed4ae20213" />


Log in to your Dropbox account and complete the authentication process.

Once authentication is complete, return to the RCP Terminal.

### If you use passwordless authentication

If you normally authenticate using a **passkey or another passwordless authentication method**, such as a fingerprint or Face ID on your laptop, you cannot complete that authentication from the RCP.

When rclone asks whether you would like to use a web browser to automatically authenticate the remote, select **No**.
<br></br>
<img width="897" height="251" alt="image" src="https://github.com/user-attachments/assets/ae520b15-f56d-4671-807a-0fa0af4bcf64" />
<img width="889" height="298" alt="image" src="https://github.com/user-attachments/assets/fbfbb793-19f6-426d-a2b2-815944ba3b82" />

You will need to complete the authentication on another computer that has rclone installed. If you do not already have rclone installed on that computer, follow the [rclone installation instructions](https://rclone.org/downloads/).

On your other computer, open a Terminal or command prompt and run:

```bash
rclone authorize "dropbox"
```

This will open a browser **on your other computer**. Log in to Dropbox using your usual authentication method, including your passkey or biometric authentication if prompted.

Once authentication is complete, return to the Terminal on your other computer. rclone will provide an authorization result.

Copy the entire authorization result, beginning with `{` and ending with `}`.

<img width="975" height="241" alt="image" src="https://github.com/user-attachments/assets/e098bcb0-4720-43b8-9cea-6f13c492dcef" />
<br></br>
Return to the **RCP Terminal** and paste the authorization result when prompted.

### Save the remote

After authentication is complete, review the configuration and select the option to **keep the existing remote**.

<img width="514" height="310" alt="image" src="https://github.com/user-attachments/assets/6489d92a-0f7c-4b94-a8b9-ece3f5d6534d" />

Your Dropbox connection is now configured.

## 4. Copy files to Dropbox

You can now copy files between the RCP and Dropbox.

For example, to copy files from an RCP project data folder to a folder in Dropbox, use:

```bash
rclone copy ~/studies/<project-name>/data <remote-name>:<dropbox-folder>
```

Replace:

* `<project-name>` with the name of your RCP project.
* `<remote-name>` with the name you gave your Dropbox remote during configuration.
* `<dropbox-folder>` with the folder in Dropbox where you want the files copied.

For example:

```bash
rclone copy ~/studies/RCS_Project-Storage-mf9/data RCP_Testing:RCP-data
```

In this example, `RCP_Testing` is the name of the remote and `RCP-data` is the destination folder in Dropbox.

For additional options and rclone commands, see the [rclone command documentation](https://rclone.org/commands/).

## Syncing files with rclone

rclone can also **sync** files between locations. However, `sync` behaves differently from `copy` and should be used with caution.

With:

```bash
rclone copy
```

rclone copies new or changed files to the destination without deleting files that are already there.

With:

```bash
rclone sync
```

rclone changes the destination so that it matches the source.

> **⚠️ Be careful when using `sync`.** Files in the destination that do not exist in the source may be **deleted**. For example, if you sync an RCP folder to a Dropbox folder that already contains other files, those additional Dropbox files could be deleted.

If your goal is simply to transfer or update files, use **`rclone copy`** rather than `rclone sync`.

Before using `sync`, you can preview what rclone would do by adding the `--dry-run` option:

```bash
rclone sync ~/studies/<project-name>/data <remote-name>:<dropbox-folder> --dry-run
```

This allows you to review the proposed changes without actually copying or deleting files.

## Additional notes

* rclone is available in the **Utility Launcher** on the RCP.
* These instructions have been tested with Dropbox.
* Other rclone storage providers may work but have not been tested by RCS.
* At this time, rclone cannot connect to OneDrive from the RCP.
* If you have questions or encounter problems using rclone on the RCP, contact **[research@hbs.edu](mailto:research@hbs.edu)**.
