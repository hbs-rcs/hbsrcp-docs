# Research Data Storage

## Transferring Project Data
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