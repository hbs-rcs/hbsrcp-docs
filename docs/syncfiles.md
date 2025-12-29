# Storage and Managing Project Files

## Storage
Each project has storage available to all members of a project. This can be accessed by clicking on the "Files" tab to the right of the Workbench:<br>

<img width="932" height="164" alt="image" src="https://github.com/user-attachments/assets/a11274fe-e86a-4630-bc66-c5afa492f534" /><br>

Please see our documentation below to learn more using this feature. 

## Transferring Files
### Uploading and Downloading Local Files

Users can upload and download local files by clicking on the "Files" tab to the right of the Workbench. 

<img width="932" height="164" alt="image" src="https://github.com/user-attachments/assets/a11274fe-e86a-4630-bc66-c5afa492f534" /><br>

To upload a file, click on the "Upload File" button next to the "Actions" Button. To upload a folder, click on the down arrow to the right of the "Upload File" button, which will reveal the option to upload a folder:

<img width="204" height="68" alt="image" src="https://github.com/user-attachments/assets/0d04d084-fceb-4cd1-876e-75c078ae54b9" /><br>

**Currently, only one file or folder up to 5GB can be uploaded/downloaded at a time by users**. To upload multiple and/or large files, one option is to compress them locally and then [extract](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/) them on the RCP. Similarly, you can [compress](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/) files on the RCP prior to downloading them localling. Detailed instructions on can be found in our [Compressing and Extracting Files Tutorial](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/). Otherwise, please use one of the methods outlined in the following sections. 

### Transferring from Cloud Storage
*Coming soon*

### Using Globus

Globus, a data transfer service, can be used to transfer multiple files at once and/or files exceeding the 5GB limit. Globus can be used to transfer data into a project space on the RCP or out of the RCP to another location. To request a Globus file transfer, please contact research@hbs.edu.

## Managing Source Code - Syncing to Git

All launchers for IDEs (including Stata, VSCode, RStudio, Jupyter and Spyder) have git installed on their base images.   To use git for sessions using these launchers, please use the terminal window for each to execute git commands.  

For a list of common git commands see the [Git Hub Cheat Sheet](https://git-scm.com/cheat-sheet).

If you are brand new to code code version control with git, [please visit this useful guide](https://docs.github.com/en/get-started/start-your-journey).


If you are using Harvard’s Github enterprise for your repositories the standard login and password do not work and you will need to use either ssh keys or tokens.  Please see
1.	[https://github.com/settings/tokens](https://github.com/settings/tokens) for using tokens  
2.	https://github.com/settings/ssh for ssh

If you have any questions or run into issues, please reach out to research@hbs.edu

## SQL Databases

RCP hosts a MySQL relational database in the cloud called [Aurora](https://aws.amazon.com/rds/aurora/). Please note that RCS provides limited support for databases. 

### Connecting to your Database 

Connection parameters, including your username, password, and hostname can be obtained by clicking on the “View Aurora Details” link in the upper right hand corner of the Workbench:  

![Aurora screenshot](/media/Aurora-details-link.png)

Otherwise, see below for sample code to connect to your database using Python. If you prefer to use R, please contact RCS for customized instructions.

#### Python

Using the [mysql python package](link: https://dev.mysql.com/doc/connector-python/en/connector-python-examples.html):

```
import mysql.connector 
# Connect to the database 
conn = mysql.connector.connect( 
    user = 'username', 
    password = 'password'', 
    host = 'host', 
    database = ''databasename')
```
