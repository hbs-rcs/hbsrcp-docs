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

![The RCP Workbench launcher list showing VSCode among eleven launchers](img/vscode-01-launcher-list.png)

Select it, give the session a name, and pick a configuration.

![The Create a session dialog with a session name and the configuration dropdown open](img/vscode-02-create-session.png)

> **💰 The configuration you pick sets your hourly RCP cost.** The dropdown shows the
> hourly rate next to each option — from roughly \$0.09/h for `General-Purpose-t2.large` up
> to about \$12.70/h for `r7i.48xlarge`. **Claude Code itself does not need a large or GPU
> node.** Unless your actual analysis requires one, a general-purpose configuration is the
> right choice.

---

## Step 2 — Connect to your session

Once the session is **Active**, click **Connect**.

![An RCP session tile showing status Active, the configuration, Cost to Date, and a Connect button](img/vscode-03-connect.png)

> **💡 Tip:** **Cost to Date** on this tile is your RCP compute cost only. Claude token usage
> is billed to your Claude account and does not appear here.

---

## Step 3 — Install the Claude Code extension

In VS Code, open the **Extensions** panel and search for `claude`. Select **Claude Code for
VS Code** by **Anthropic** and click **Install**.

![The VS Code Extensions marketplace filtered to claude, with Claude Code for VS Code by Anthropic selected](img/vscode-04-extension-marketplace.png)

> **⚠️ Check the publisher.** Search results include several community extensions with
> similar names. You want the one published by **Anthropic**.

Once installed, the orange Claude starburst icon appears in the top-right of the editor and
in the left activity bar.

![VS Code with the Claude starburst icon visible in the top-right of the editor toolbar](img/vscode-05-extension-installed.png)

> **⚠️ The extension does not survive a Terminate.** It persists if you **Stop** the session,
> but a terminated session resets to a clean environment and you will reinstall it. See
> [Stop vs. Terminate](claude_code_setup.md#one-thing-to-know-before-you-start-stop-vs-terminate).

---

## Step 4 — Start logging in

Click the Claude icon. The panel opens and asks how you want to log in.

![The Claude Code panel asking how do you want to log in, with Claude.ai Subscription, Anthropic Console, and Bedrock/Foundry/Vertex options](img/vscode-06-login-options.png)

For an **HBS enterprise or personal Claude subscription**, click **Claude.ai Subscription**.

Choose **Anthropic Console** instead only if you are paying for API usage through your own
Console account.

---

## Step 5 — Cancel the browser popup

VS Code will offer to open an external website. **Click Cancel.**

![A dialog asking Do you want code-server to open the external website, with the Cancel button circled](img/vscode-07-cancel-external-browser.png)

> **Why cancel?** `code-server` is running on a remote RCP machine that has no browser of its
> own. Letting it try to "open" the URL there does nothing useful. You need that URL in the
> browser on *your* computer instead — which is the next step.

---

## Step 6 — Copy the authorization URL

After cancelling, the panel shows a **Continue in browser** screen with the URL in a text
field and a copy button beside it.

![The Continue in browser screen showing the authorization URL, a copy button, and a field to paste an authorization code](img/vscode-08-continue-in-browser.png)

Click the copy button to copy the full URL. **Leave this panel open** — you will come back to
the code field at the bottom.

---

## Step 7 — Authorize in your own browser

Paste the URL into a new tab in the browser **on your local machine** and log in with your
Claude credentials. You will see the authorization screen:

![The Claude authorization screen listing the permissions Claude Code is requesting, with Authorize and Decline buttons](img/vscode-09-authorize.png)

Click **Authorize**.

You will then be shown an authentication code.

![The Authentication code screen with the code redacted and a Copy code button](img/vscode-10-auth-code.png)

Click **Copy code**.

> **🔒 Treat this code like a password.** It grants access to your Claude account. Do not
> paste it into a shared document, a ticket, or a chat.

---

## Step 8 — Paste the code back into VS Code

Return to the Claude Code panel in RCP and paste the code into the **Or, paste your
authorization code manually** field, then click **Continue**.

![The Continue in browser panel with the authorization code pasted into the manual entry field](img/vscode-11-paste-code.png)

---

## Step 9 — Start using Claude Code

Claude Code is now authenticated. The panel shows the model in use and a prompt box.

![The Claude Code panel in VS Code, docked to the right of the editor, showing the model selector and the Ask Claude to edit prompt box](img/vscode-12-claude-panel.png)

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
