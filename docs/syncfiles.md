# Transferring and Managing Project Files

## Transferring Files
### Uploading and Downloading Local Files

Users can upload and download local files by clicking on the "Files" tab to the right of the Workbench. 

<img width="932" height="164" alt="image" src="https://github.com/user-attachments/assets/a11274fe-e86a-4630-bc66-c5afa492f534" /><br>

To upload a file, click on the "Upload File" button next to the "Actions" button. To upload a folder, click on the down arrow to the right of the "Upload File" button, which will reveal the option to upload a folder:

<img width="204" height="68" alt="image" src="https://github.com/user-attachments/assets/0d04d084-fceb-4cd1-876e-75c078ae54b9" /><br>

**Currently, only one file or folder up to 5GB can be uploaded/downloaded at a time by users**. To upload multiple and/or large files, one option is to compress them locally and then [extract](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/) them on the RCP. Similarly, you can [compress](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/) files on the RCP prior to downloading them localling. Detailed instructions on can be found in our [Compressing and Extracting Files Tutorial](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/). Otherwise, please use one of the methods outlined in the following sections. 

### Transferring from Cloud Storage
*Coming soon*

### Using Globus

Globus, a data transfer service, can be used to transfer multiple files at once and/or files exceeding the 5GB limit. Globus can be used to transfer data into a project space on the RCP or out of the RCP to another location. In order to use Globus, you will need to establish your project as an end point for Globus. To do this, log into the Globus transfer application at www.globus.org.  You will need to select Harvard University as your institution followed by entering your Harvard Key credentials and password. Please note that only HBS credentials will have access to HBS resources. Credentials from other schools will not work properly.

Once logged in, navigate to the file manager tab and locate the Harvard Business School S3 Collection by searching for this collection in the Collection dialog box.

<img width="1663" height="541" alt="image" src="https://github.com/user-attachments/assets/892886ff-ed87-421e-9dc7-bd51f38e8709" />

After selecting the "Harvard Business School S3 Storage" Collection, you should see the following dialog:
<img width="982" height="651" alt="image" src="https://github.com/user-attachments/assets/1860388f-dc61-42df-ac43-9e00d1acade2" />
Click the continue button and you will be brought to this dialog box:
<img width="867" height="428" alt="image" src="https://github.com/user-attachments/assets/202ec06d-29fa-498d-977b-3d928ded4203" />

Enter the AWS IAM Access Key ID and AWS IAM Secret Key provided to you by the Research Technology team for your project. If you don't have an Access Key ID or Secret Key ID, please contact RCS at [research@hbs.edu](research@hbs.edu) and request them for you project. If you are not the project owner, you will need permission from the project owner to obtain these Key IDs.

After entering the Key IDs, you should be able to see the directory listing of your project, as well as be able to upload and download files as shown below.
<img width="1306" height="1016" alt="image" src="https://github.com/user-attachments/assets/66dd65c0-5e6f-4bb9-b7d1-bbe7762d59f6" />

If you are transferring very large files, we recommend transfer from another Globus endpoint (such as the Harvard Business School DTN, attached to the HBSGrid, or by creating your own endpoint using Globus Personal).

If you need help at any point along the way, please contact [research@hbs.edu](mailto:research@hbs.edu).

## Managing Source Code - Syncing to Git

All launchers for IDEs (including Stata, VSCode, RStudio, Jupyter and Spyder) have git installed on their base images.   To use git for sessions using these launchers, please use the terminal window for each to execute git commands.  

For a list of common git commands see the [Git Hub Cheat Sheet](https://git-scm.com/cheat-sheet).

If you are brand new to code code version control with git, [please visit this useful guide](https://docs.github.com/en/get-started/start-your-journey).


If you are using Harvard’s Github enterprise for your repositories the standard login and password do not work and you will need to use either ssh keys or tokens.  Please see
1.	[https://github.com/settings/tokens](https://github.com/settings/tokens) for using tokens  
2.	https://github.com/settings/ssh for ssh

If you have any questions or run into issues, please reach out to [research@hbs.edu](research@hbs.edu).
