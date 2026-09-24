---
title: "Claude Code in VS Code"
author: "Samah Karim"

tags:
  - claude
  - vscode
---
# Claude Code in VS Code

You can install Claude Code into RCP's **VSCode** launcher as an extension. Claude works in a
panel beside your files, and each change it proposes appears in the editor as a
before-and-after you accept or reject.

> Prefer a plain terminal? See the [Claude Code launcher guide](claude_code_terminal.md).
> New to all of this? Start with [Setup](claude_code_setup.md).

> **⚠️ Claude Code usage is billed separately to your HBS or personal Claude account**, and
> metered by tokens. Your RCP compute is billed separately again. See
> [Cost, billing, and data handling](cost_and_data.md).

---

## Step 1 — Launch a VS Code session

> **⚠️ Important:** Please ensure that the project owner has
> [enabled the VS Code launcher](claude_code_setup.md#2-your-project-owner-must-enable-the-launcher).

Inside RCP, go to the **Workbench** tab and find **VSCode** among the available software
options.

<img width="1745" height="884" alt="image" src="https://github.com/user-attachments/assets/50d4e5b3-770a-4030-a32b-9ee2af05f27d" />

Select it, give the session a name, and pick a configuration.

<img width="702" height="816" alt="image" src="https://github.com/user-attachments/assets/db58dc37-0b31-46b4-9fc4-a920cc0a29de" />

> **💰 The configuration you pick sets your hourly RCP cost.** The dropdown shows the
> hourly rate next to each option — from roughly \$0.09/h for `General-Purpose-t2.large` up
> to about \$12.70/h for `r7i.48xlarge`. **Claude Code itself does not need a large or GPU
> node.** Unless your actual analysis requires one, a general-purpose configuration is the
> right choice.

---

## Step 2 — Connect to your session

Once the session is **Active**, click **Connect**.

<img width="613" height="449" alt="image" src="https://github.com/user-attachments/assets/ebcdf688-119b-4337-9fcf-50fe286d3dd7" />

> **💡 Tip:** **Cost to Date** on this tile is your RCP compute cost only. Claude token usage
> is billed to your Claude account and does not appear here.

---

## Step 3 — Install the Claude Code extension

In VS Code, open the **Extensions** panel and search for `claude`. Select **Claude Code for
VS Code** by **Anthropic** and click **Install**.

<img width="1068" height="521" alt="image" src="https://github.com/user-attachments/assets/35323bf0-5a35-4405-a5aa-09c201fcadf0" />

> **⚠️ Check the publisher.** Search results include several community extensions with
> similar names. You want the one published by **Anthropic**.

Once installed, the orange Claude starburst icon appears in the top-right of the editor and
in the left activity bar.

<img width="1451" height="895" alt="image" src="https://github.com/user-attachments/assets/45867091-6e5c-491b-a983-1765ed62b35f" />


> **⚠️ The extension does not survive a Terminate.** It persists if you **Stop** the session,
> but a terminated session resets to a clean environment and you will reinstall it. See
> [Stop vs. Terminate](claude_code_setup.md#one-thing-to-know-before-you-start-stop-vs-terminate).

---

## Step 4 — Start logging in

Click the Claude icon. The panel opens and asks how you want to log in.

<img width="1170" height="795" alt="image" src="https://github.com/user-attachments/assets/33596cd8-c755-4718-933e-74409c86af41" />

For an **HBS enterprise or personal Claude subscription**, click **Claude.ai Subscription**.

Choose **Anthropic Console** instead only if you are paying for API usage through your own
Console account.

---

## Step 5 — Cancel the browser popup

VS Code will offer to open an external website. **Click Cancel.**

<img width="1383" height="753" alt="image" src="https://github.com/user-attachments/assets/97612dd1-1e27-4cf0-84b2-e48130927404" />

> **Why cancel?** `code-server` is running on a remote RCP machine that has no browser of its
> own. Letting it try to "open" the URL there does nothing useful. You need that URL in the
> browser on *your* computer instead — which is the next step.

---

## Step 6 — Copy the authorization URL

After cancelling, the panel shows a **Continue in browser** screen with the URL in a text
field and a copy button beside it.

<img width="958" height="860" alt="image" src="https://github.com/user-attachments/assets/1b91f724-e839-4be9-a3bc-d144fc14a7e2" />

Click the copy button to copy the full URL. **Leave this panel open** — you will come back to
the code field at the bottom.

---

## Step 7 — Authorize in your own browser

Paste the URL into a new tab in the browser **on your local machine** and log in with your
Claude credentials. You will see the authorization screen:

<img width="1274" height="1374" alt="image" src="https://github.com/user-attachments/assets/2384198b-0310-4813-acd3-c7dd13378e82" />


Click **Authorize**.

You will then be shown an authentication code.

<img width="1874" height="674" alt="image" src="https://github.com/user-attachments/assets/68db92cf-5685-4894-a247-ed1eda6c3092" />

Click **Copy code**.

> **🔒 Treat this code like a password.** It grants access to your Claude account. Do not
> paste it into a shared document, a ticket, or a chat.

---

## Step 8 — Paste the code back into VS Code

Return to the Claude Code panel in RCP and paste the code into the **Or, paste your
authorization code manually** field, then click **Continue**.

<img width="874" height="730" alt="image" src="https://github.com/user-attachments/assets/c4deb45a-1c4d-407e-ac66-e97c0ea6b65b" />

---

## Step 9 — Start using Claude Code

Claude Code is now authenticated. The panel shows the model in use and a prompt box.

<img width="1624" height="1442" alt="image" src="https://github.com/user-attachments/assets/2f490a16-4e38-4e26-8d53-6e6c2dab2d5f" />

A few things worth noticing in that panel:

- **Model selector** (bottom left of the prompt box) — shows which model you are talking to.
  Larger models cost more per token.
- **Permission mode** (bottom right, e.g. *Manual*) — controls how much Claude can do without
  asking you first. **Manual** asks before each action. Keep it there until you trust what
  a given task is doing to your project space.
- **Terminal fallback** — the panel notes you can switch to the terminal experience in
  Settings, or just run `claude` in VS Code's integrated terminal.

---

## What Claude can reach

Claude Code works from the folder that is open in VS Code. That folder, and everything below
it, is what Claude can read and change — anything outside it is out of reach.

To point Claude somewhere else, use **File → Open Folder** and choose the directory you want
to work in. The Claude panel picks up the new folder along with the rest of the editor.

---

## Where to go next

- **[Tips, patterns, and `CLAUDE.md`](rcp_tips_tricks.md)** — getting good results efficiently
- **[Cost, billing, and data handling](cost_and_data.md)** — the two-meter problem

---

## Getting help

📧 **[research@hbs.edu](mailto:research@hbs.edu)**
