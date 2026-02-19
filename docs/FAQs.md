# HBS Research Computing Platform (RCP) – Frequently Asked Questions

🔐 Access & Project Setup

<a id="how-do-i-get-access"></a>

??? note How do I get access to RCP?

    Visit the RCP documentation homepage and follow the access instructions:
    
    🔗 https://hbs-rcs.github.io/hbsrcp-docs/
    
    You must log into RCP at least once before being added to a project.
    
    If you need help, contact [**research@hbs.edu**](mailto:research@hbs.edu).

<a id="what-is-a-project-space"></a>
<details>
<summary>What is a project space?</summary>

A project space is a shared workspace where the following are managed:

- Data  
- Compute sessions  
- Storage  
- Permissions  
- Costs  

All work in RCP happens inside a project space.

Learn more:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/

</details>

<a id="who-can-add-me"></a>
<details>
<summary>Who can add me to a project?</summary>

Only the **Project Owner** can add users to a project by reaching out to [**research@hbs.edu**](mailto:research@hbs.edu).

You must log into RCP at least once before the Project Owner can add you.

</details>

<a id="no-projects-visible"></a>
<details>
<summary>I logged in but don’t see any projects. Why?</summary>

Most likely:

- You have not been added to a project yet, or  
- You have not logged in at least once before being added  

Contact your project owner or [**research@hbs.edu**](mailto:research@hbs.edu).

</details>

<a id="data-upload-storage"></a>
# 💾 Data Upload & Storage

<a id="upload-file"></a>
<details>
<summary>How do I upload a file from my laptop?</summary>

1. Open your project Workbench.  
2. Click the **Files** tab.  
3. Click **Upload File**.  
4. Select your file.  

File transfer guide:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/

</details>

<a id="file-size-limit"></a>
<details>
<summary>Is there a file size limit?</summary>

- Web uploads support single files up to 5GB.  
- For large or multiple files, use **Globus** or compress your files.

More details:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/

</details>

<a id="where-is-my-data"></a>
<details>
<summary>Where is my data stored?</summary>

Your data is stored in your project’s S3-backed storage, accessible through:

- The Files tab  
- Your launchers (RStudio, Jupyter, VSCode)

Storage documentation:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/storage_software/

</details>

<a id="can-i-use-git"></a>
<details>
<summary>Can I use Git?</summary>

Yes. Git can be used within launchers such as VSCode or RStudio terminals.

Documentation:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/#managing-source-code-syncing-to-git

</details>

<a id="launchers-compute"></a>
# 💻 Launchers & Compute Sessions

<a id="what-is-a-launcher"></a>
<details>
<summary>What is a launcher?</summary>

A launcher is an interactive compute session, such as:

- RStudio  
- JupyterLab  
- VSCode  
- SageMaker environments  

Launchers guide:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/

</details>

<a id="start-session"></a>
<details>
<summary>How do I start a session?</summary>

1. Open your project Workbench.  
2. Select a launcher.  
3. Choose instance size and type.  
4. Click **Create**.  
5. Click **Connect** when ready.  

Detailed instructions:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/

</details>

<a id="stop-vs-terminate"></a>
<details>
<summary>What’s the difference between Stop and Terminate?</summary>

- **Stop**: Pauses compute. You can restart later.  
- **Terminate**: Permanently deletes the session.  

Stopping prevents ongoing compute charges.

More details:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/

</details>

<a id="available-packages-tools"></a>
# 📦 Available Software & Tools

<a id="available-software-list"></a>
<details>
<summary>Available Packages and Tools</summary>

RCS and IT are continually working to add functionality to the RCP. As of February 2026, the available software and tools include:

- Aurora Database 
- JupyterLab  
- RStudio  
- SageMaker Canvas
- SageMaker Notebook
- Spyder  
- Stata  
- VSCode  

For more details on software environments and storage:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/storage_software/

</details>

<a id="install-packages"></a>
<details>
<summary>Can I install additional packages?</summary>

Yes. You can install R or Python packages within your launcher session.

Installation guidance:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/storage_software/

</details>

<a id="costs-billing"></a>
# 💰 Costs & Billing

All costs will be covered by DRFD and HBS IT through FY26 using a reimbursement model.

<a id="when-am-i-charged"></a>
<details>
<summary>When am I charged?</summary>

You are charged while a session is **running**.

Stopped sessions incur minimal storage costs.

Billing documentation:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/billing/

</details>

<a id="monitor-spending"></a>
<details>
<summary>How can I monitor project spending?</summary>

Project Owners can view usage and cost dashboards within the project.

More information:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/

</details>

<a id="reduce-costs"></a>
<details>
<summary>How do I reduce costs?</summary>

- Stop sessions when not actively using them  
- Choose appropriately sized instances  
- Terminate unused sessions  

Billing guide:  
🔗 https://hbs-rcs.github.io/hbsrcp-docs/billing/

</details>

<a id="security-classification"></a>
# 🔒 Security & Data Classification

<a id="supported-security-levels"></a>
<details>
<summary>What data security levels are supported?</summary>

RCP supports research workloads aligned with Harvard’s data security classification Levels 1 to 4.

For official guidance:  
🔗 https://privsec.harvard.edu/

If you’re unsure about your data classification, consult your Project Owner.

</details>

<a id="troubleshooting-support"></a>
# 🛠 Troubleshooting & Support

</details>

<a id="contact-support"></a>
<details>
<summary>Who do I contact for help?</summary>

Email: [**research@hbs.edu**](mailto:research@hbs.edu).

This is the central support channel for:

- Access issues  
- Billing questions  
- Technical problems  
- Documentation clarifications  

</details>
