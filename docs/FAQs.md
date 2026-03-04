# HBS Research Computing Platform (RCP) – Frequently Asked Questions

## 🔄 Transition from HBSGrid to the RCP Transition from HBSGrid to the RCP
??? note "Why is the HBS Research Grid being retired?"

    HBS is transitioning to a more modern, scalable, and flexible research computing environment. The cloud-based Research Computing Platform (RCP) offers enhanced performance, greater elasticity, access to GPUs, and integrated data science tools that better support evolving research needs. Learn more about RCP  

??? note "Do I need to take action today? Will my current projects and home directory be affected right now?" 

    No immediate action is required. All active and archived projects, along with home directories, on the HBSGrid remain fully accessible at this time. You may continue your work without interruption.  

??? note "What should I do if I am starting a new research project?"

    Many new project spaces can be provisioned on the RCP. Please see the available software and tools [below](https://hbs-rcs.github.io/hbsrcp-docs/FAQs/#available-software-tools), or contact [research@hbs.edu](mailto:research@hbs.edu) with a description of your work if you'd like to discuss using the RCP. We’re happy to discuss your project requirements, or to answer any other questions you may have.

## 🔐 Access & Project Setup

??? note "How do I get access to RCP?"

    Visit the RCP documentation homepage and follow the access instructions:

    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/](https://hbs-rcs.github.io/hbsrcp-docs/)

    You must log into RCP at least once before being added to a project.

    If you need help, contact [**research@hbs.edu**](mailto:research@hbs.edu).

??? note "What is a project space?"

    A project space is a shared workspace where the following are managed:

    - Data  
    - Compute sessions  
    - Storage  
    - Permissions  
    - Costs  

    All work in RCP happens inside a project space.

    Learn more:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/)

??? note "Who can add me to a project?"

    Only the **Project Owner** can add users to a project by reaching out to [**research@hbs.edu**](mailto:research@hbs.edu).

    You must log into RCP at least once before the Project Owner can add you.

??? note "I logged in but don’t see any projects. Why?"

    Most likely:

    - You have not been added to a project yet, or  
    - You have not logged in at least once before being added  

    Contact your Project Owner or [**research@hbs.edu**](mailto:research@hbs.edu).

## 💾 Data Upload & Storage

??? note "How do I upload a file from my laptop?"

    1. Open your project Workbench.  
    2. Click the **Files** tab.  
    3. Click **Upload File**.  
    4. Select your file.  

    File transfer guide:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

??? note "Is there a file size limit?"

    - Web uploads support single files up to 5GB.  
    - For large or multiple files, use **Globus** or compress your files.

    More details:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/)

??? note "Where is my data stored?"

    Your data is stored in your project’s S3-backed storage, accessible through:

    - The Files tab  
    - Your launchers (RStudio, Jupyter, VSCode)

    Storage documentation:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/storage_software/](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

??? note "Can I use Git?"

    Yes. Git can be used within launchers such as VSCode or RStudio terminals.

    Documentation:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/#managing-source-code-syncing-to-git](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/#managing-source-code-syncing-to-git)

## 💻 Launchers & Compute Sessions

??? note "What is a launcher?"

    A launcher is an interactive compute session, such as:

    - RStudio  
    - JupyterLab  
    - VSCode  
    - SageMaker environments  

    Launchers guide:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

??? note "How do I start a session?"

    1. Open your project Workbench.  
    2. Select a launcher.  
    3. Choose instance size and type.  
    4. Click **Create**.  
    5. Click **Connect** when ready.  

    Detailed instructions:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

??? note "What’s the difference between Stop and Terminate?"

    - **Stop**: Pauses compute. You can restart later.  
    - **Terminate**: Permanently deletes the session.  

    Stopping prevents ongoing compute charges.

    More details:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/](https://hbs-rcs.github.io/hbsrcp-docs/launchers_sessions/)

## 📦 Available Software & Tools

??? note "Available Packages and Tools"

    RCS and IT are continually working to add functionality to the RCP. As of February 2026, the available software and tools include:

    - Aurora Database 
    - JupyterLab  
    - RStudio  
    - SageMaker Canvas
    - SageMaker Notebook
    - Spyder  
    - Stata  
    - VSCode  

    Coming Soon!
    
    - Mathematica 
    - MatLab 
    - SAS  
    - Batch processing capabilities
    - Parallel processing

    For more details on software environments and storage:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/storage_software/](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

??? note "Can I install additional packages?"

    Yes. You can install R or Python packages within your launcher session.

    Installation guidance:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/storage_software/](https://hbs-rcs.github.io/hbsrcp-docs/storage_software/)

## 💰 Costs & Billing

All costs will be covered by DRFD and HBS IT through FY26 using a reimbursement model.

??? note "When am I charged?"

    You are charged while a session is **running**.

    Stopped sessions incur minimal storage costs.

    Billing documentation:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/billing/](https://hbs-rcs.github.io/hbsrcp-docs/billing/)

??? note "How can I monitor project spending?"

    Project Owners can view usage and cost dashboards within the project.

    More information:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/](https://hbs-rcs.github.io/hbsrcp-docs/manageprojects/)

??? note "How do I reduce costs?"

    - Stop sessions when not actively using them  
    - Choose appropriately sized instances  
    - Terminate unused sessions  

    Billing guide:  
    🔗 [https://hbs-rcs.github.io/hbsrcp-docs/billing/](https://hbs-rcs.github.io/hbsrcp-docs/billing/)

## 🔒 Security & Data Classification

??? note "What data security levels are supported?"

    RCP supports research workloads aligned with Harvard’s data security classification Levels 1 to 4.

    For official guidance:  
    🔗 [https://privsec.harvard.edu/](https://privsec.harvard.edu/)

    If you’re unsure about your data classification, consult your Project Owner.

## 🛠 Troubleshooting & Support

??? note "Who do I contact for help?"

    Email: [**research@hbs.edu**](mailto:research@hbs.edu).

    This is the central support channel for:

    - Access issues  
    - Billing questions  
    - Technical problems  
    - Documentation clarifications
