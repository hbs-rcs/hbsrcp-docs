# 📦 Project Spaces, Storage, and Available Software and Analysis Tools
## Project Spaces
Project owners can request new projects using this [form](https://secure.hbs.edu/accountManagement/secure/research-computing-platform/projectspace/new). To add additional team members to a project space, contact research@hbs.edu. Remember that you will not be able to request a project space or be added to an existing project until you have logged into the RCP at least once.

The landing page of the RCP displays tiles with all projects that you have access to:

<img width="335" height="221" alt="image" src="https://github.com/user-attachments/assets/2254541a-c40a-44ca-97ae-85fd344be337" /><br>

Clicking on a project will bring you to the project workbench.  The workbench displays active [sessions](launchers_sessions.md#starting-sessions) on the top half of the page and available [launchers](launchers_sessions.md), each corresponding to different [analysis tools](storage_software.md#available-software), on the bottom half of the page: 

<img width="932" height="416" alt="image" src="https://github.com/user-attachments/assets/7d0a3ef0-ec55-4bcc-bc5f-d5e5bf6a656e" />

## Storage
### S3 Bucket
Each project has shared [S3 storage](https://aws.amazon.com/s3/) available to all members of a project. This can be accessed by clicking on the "Files" tab to the right of the Workbench:<br>

<img width="932" height="164" alt="image" src="https://github.com/user-attachments/assets/a11274fe-e86a-4630-bc66-c5afa492f534" /><br>

Please see our documentation about [Transferring Files](syncfiles.md) to learn more using this feature. 

### Database
The RCP offers database capabilities through a back-end connection to [Amazon Aurora](https://aws.amazon.com/rds/aurora/). Connection parameters, including the username, password, and hostname can be obtained by the Project Owner in the Project Management tab. Within the Servcies section, click on the three vertical dots next to the Aurora DB service and select "View Details" to view the parameters as shown below.

<img width="596" height="200" alt="image" src="https://github.com/user-attachments/assets/d414855f-4162-4aa7-9796-bc4719667df4" />

See below for sample code to connect to your database using Python. If you prefer to use R, please contact RCS for customized instructions.

#### Python

Using the [mysql](https://dev.mysql.com/doc/connector-python/en/connector-python-examples.html) python package:

```
import mysql.connector 
# Connect to the database 
conn = mysql.connector.connect( 
    user = 'username', 
    password = 'password'', 
    host = 'host', 
    database = ''databasename')
```


## Available software and analysis tools

The RCP launchers feature the most commonly used research software and analysis tools, including *Rstudio*, *Spyder*, *VSCode*, and *Stata*. Additionally, if applicable for the software, each launcher is preloaded with commonly used packages and modules. 

### Installing Packages or Modules

If the package that you need to use is **not** preloaded, you can install it using the usual commands.

!!! important inline end
     **Please note that the packages and modules you install are only available within a launcher, and not across the project's launchers**. If you terminate the launcher, these packages and modules will be deleted. 

#### Installing R Packages

Using the standard command for  `install.packages()` command from within RStudio will download and install the specified packages. 

``` sh
install.packages('somepkg')
```
#### Installing Python Modules

Python modules can be installed using the `pip install` command:

``` sh
pip install some_module
```

To update/upgrade a module already installed, include also the `--upgrade` option: 

``` sh
pip install --upgrade some_module
```


