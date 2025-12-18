# Storage and Managing Project Files

## Managing Source Code - Syncing to Git

All launchers for IDEs (including Stata, VSCode, RStudio, Jupyter and Spyder) have git installed on their base images.   To use git for sessions using these launchers, please use the terminal window for each to execute Git commands.  

For a list of common git commands see the [Git Hub Cheat Sheet](https://git-scm.com/cheat-sheet).

If you are brand new to code code version control with git, [please visit this useful guide](https://docs.github.com/en/get-started/start-your-journey).


If you are using Harvard’s Github enterprise for your repositories the standard login and password do not work and you will need to use either ssh keys or tokens.  Please see
1.	[https://github.com/settings/tokens](https://github.com/settings/tokens) for using tokens  
2.	https://github.com/settings/ssh for ssh

If you have any questions or run into issues, please reach out to research@hbs.edu


## Transferring Files
*Coming soon*

### Uploading and Downloading Local Files

### Transferring from Cloud Storage

### Using Globus

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
