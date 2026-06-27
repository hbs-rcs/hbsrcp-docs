---
title: "Using Claude Code on the RCP"
author: "Liz Kernan and Melissa Velez"

tags:
  - claude
  - terminal
---

# Claude Code on the HBS Research Computing Platform {#claude} 
================

## Overview

Claude Code is Anthropic's command-line AI coding assistant. On the HBS Research Computing Platform (RCP), Claude Code runs inside a launcher from a Terminal window. This guide walks through finding the ClaudeCode launcher, opening a Terminal, and starting a Claude Code session.

> **⚠️ Important: Claude Code usage is billed separately to your HBS or personal account**
> Every Claude Code session you run is tied to your Claude Code account, whether that's through HBS or a personal account. Usage is metered by **tokens** (the units of text Claude reads and writes), and costs can add up quickly on long sessions, large codebases, or big files. Please be mindful of usage and follow the [best practices](#best-practices-for-responsible-use) at the end of this guide before starting long or repeated sessions.

## Benefits of Running Claude Code on RCP

A benefit of using Claude Code on the RCP is that it runs entirely within your project space. This means that if Claude Code does something unintended — overwrites a file, runs a bad script — the damage is contained to that environment rather than your local machine or personal filesystem. Claude Code can only read and write within that space, which also reduces the risk of data leaking to unintended destinations.

---

## Step 1 — Find ClaudeCode on the RCP

> **⚠️ Important: To use Claude Code, please ensure that the project owner has [enabled the ClaudeCode launcher](manageprojects.md/#configure-services).** The _first_ time you launch a Claude Code session, it will take about 10 minutes to provision.

Inside RCP, go to the **Workbench** tab and look for the **ClaudeCode** launcher among the available software options.
<img width="734" height="458" alt="image" src="https://github.com/user-attachments/assets/024e7dde-6ed4-4690-b803-734680da968a" />


Select **ClaudeCode** and launch a new session as you would for any other RCP launcher.

---

## Step 2 — Connect to Your Session

Once your session has started, click **Connect** on your ClaudeCode session.
<img width="630" height="492" alt="image" src="https://github.com/user-attachments/assets/f9b40ac7-f793-459c-bfad-c1af41c0b49d" />


> **💡 Tip:** Keep an eye on the **Cost to Date** field in your session. This reflects compute costs for the session and is separate from Claude Code's own token usage, which is billed independently.

---

## Step 3 — Open a Terminal Window

Claude Code runs inside a Linux environment. To open a Terminal window, follow these two steps:

1. Click the **oval/grid button** in the top-left corner of the desktop to open the application menu.
<img width="900" height="400" alt="image" src="https://github.com/user-attachments/assets/4b9e01d3-3c92-4431-ad2a-2eaaee559ac4" />

2. In the app grid at the bottom right of the screen, find and click the **Terminal** icon to open a shell window.
<img width="600" height="442" alt="image" src="https://github.com/user-attachments/assets/13811b66-9f1f-4756-899f-6cb868deb64c" />

---

## Step 4 — Launch Claude Code

If you would like your project's storage space to be Claude Code's working directory, navigate to that folder. In the Terminal:

```
cd /studies/<yourprojectspacename>
```

Once you are in your working directory, type `claude` and press **Enter** to launch Claude Code:

<img width="900" height="383" alt="image" src="https://github.com/user-attachments/assets/961b501e-8653-41f6-8f8b-61fa324d0b01" />

> **💡 Tip:** The first time you run the `claude` command, you will be asked to select your text color preference and then how you would like to log in. Most users will select option 1 if using an HBS or personal subscription. Selecting this will open a browser where you can log in with your credentials, and then paste the token back into the Claude Code Terminal if prompted.

---

## Step 5 — Start Using Claude Code

Claude Code will start up and display a welcome screen with the model name, your account, and the working directory. You can then type requests directly at the prompt.

<img width="900" height="513" alt="image" src="https://github.com/user-attachments/assets/51875e94-e488-491b-934e-7a95823845c0" />


You can now use Claude Code to do all of the following from within this terminal session:

- Read, write, and edit files
- Run and debug code
- Answer questions about your project

---

## Token Usage and Billing — Please Read

Claude Code usage on the RCP is tied to your Claude account (HBS or personal) and **billed separately to that account**.

Unlike a fixed-cost license, Claude Code usage is **metered by tokens** — the more you read, write, and ask Claude to process, the more it costs. Large files, long conversations, and repeated runs over big codebases all increase usage.

---

## Best Practices for Responsible Use

- **Close or exit** Claude Code sessions when you are done working, rather than leaving them open indefinitely.
- **Be specific and concise** in your requests — focused prompts use fewer tokens than open-ended ones.
- **Avoid pasting very large files or datasets** directly into the conversation unless necessary; point Claude Code to the file path instead.
- **Break large tasks into smaller steps** rather than asking for an entire project to be generated at once.
- If you are working on a long-running task, **periodically check in** and confirm progress rather than letting the session run unattended for hours.
- **Consider using Git** for version control. Because Claude Code can make changes across multiple files quickly, Git provides a safety net to track, review, and roll back unintended edits.

---

## Getting Help

If you have questions about Claude Code or the RCP, the HBS Research Computing team is here to help.

📧 **Email:** [research@hbs.edu](mailto:research@hbs.edu)
 
