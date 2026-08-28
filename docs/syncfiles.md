# Transferring and Managing Project Files

## Transferring Files
## Uploading and Downloading Local Files Using the Files Tab

Users can upload and download local files by clicking on the "Files" tab to the right of the Workbench. 

<img width="932" height="164" alt="image" src="https://github.com/user-attachments/assets/a11274fe-e86a-4630-bc66-c5afa492f534" /><br>

To upload a file, click on the "Upload File" button next to the "Actions" button. To upload a folder, click on the down arrow to the right of the "Upload File" button, which will reveal the option to upload a folder:

<img width="204" height="68" alt="image" src="https://github.com/user-attachments/assets/0d04d084-fceb-4cd1-876e-75c078ae54b9" /><br>

**Currently, only one file or folder up to 5GB can be uploaded/downloaded at a time by users**. To upload multiple and/or large files, one option is to compress them locally and then [extract](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/) them on the RCP. Similarly, you can [compress](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/) files on the RCP prior to downloading them localling. Detailed instructions on can be found in our [Compressing and Extracting Files Tutorial](https://hbs-rcs.github.io/hbsrcp-docs/tutorials/compressextract/). Otherwise, please use one of the methods outlined in the following sections. 

## Special Note on Uploading Files from the HBSGrid to the RCP Using the Files Tab

As the HBSGrid prepares for retirement in FY27, we recommend creating RCP project spaces to replace projects currently hosted on the HBSGrid. For large data transfers, we recommend using [Globus](https://hbs-rcs.github.io/hbsrcp-docs/syncfiles/#using-globus). For smaller transfers, you can use the RCP "Files" interface to upload data directly from the HBSGrid.

**1.Log in to the RCP**

In NoMachine, open a browser and log in to the RCP.

<img width="749" height="304" alt="image" src="https://github.com/user-attachments/assets/10b652fe-f0e9-4984-9ead-ffa76d364b34" />


**2.Select the RCP Project Space**

Navigate to the RCP project space that will receive the data. Select the "Files" tab. To upload a folder, click the arrow next to "Upload File", then select "Upload Folder".

<img width="845" height="135" alt="image" src="https://github.com/user-attachments/assets/27f4532b-a92c-4989-a149-0eaf22fc9a6b" />


**3.Select and Upload the HBSGrid Folder**

Navigate to your HBSGrid project space and select the folder you want to transfer. Click "Upload", then review the selected files and click "Upload" again to confirm.

<img width="320" height="428" alt="image" src="https://github.com/user-attachments/assets/a4d71abd-572d-4b53-b6f8-b5f3b72952e4" />

## Using Globus

!!! important
    Directories created via Globus may initially appear as **0-byte files**. This happens because folders transferred through Globus are stored in Amazon S3 (your project space) with the content type `application/x-globus-dir-placeholder`, which S3 treats as a file rather than a directory. After transferring folders through Globus, open each folder once from the RCP **Files** tab so its content type is updated and recognized as a directory, or, if using an active utility session, restart the session. 

Globus, a data transfer service, can be used to transfer multiple files at once and/or files exceeding the 5GB limit. Globus can be used to transfer data into a project space on the RCP or out of the RCP to another location. In order to use Globus, you will need to establish your project as an end point for Globus. To do this, log into the Globus transfer application at www.globus.org.  You will need to select Harvard University as your institution followed by entering your Harvard Key credentials and password. Please note that only HBS credentials will have access to HBS resources. Credentials from other schools will not work properly.

Once logged in, navigate to the file manager tab and locate the **Harvard Business School S3 Storage Collection** by searching for this collection in the Collection dialog box.

<img width="1663" height="541" alt="image" src="https://github.com/user-attachments/assets/892886ff-ed87-421e-9dc7-bd51f38e8709" />

After selecting the **"Harvard Business School S3 Storage"** Collection, authenticate (if needed), and then you should see the following dialog:
<img width="982" height="651" alt="image" src="https://github.com/user-attachments/assets/1860388f-dc61-42df-ac43-9e00d1acade2" />
Click the continue button and you will be brought to this dialog box:
<img width="867" height="428" alt="image" src="https://github.com/user-attachments/assets/202ec06d-29fa-498d-977b-3d928ded4203" />

Enter the AWS IAM Access Key ID and AWS IAM Secret Key provided to you by the Research Technology team for your project. If you don't have an Access Key ID or Secret Key ID, please fill out [this form](https://forms.cloud.microsoft/r/iV8unLm4jq) to request them for your project.

After entering the Key IDs, click on "File Manager," and then you should be able to see the directory listing of your project, as well as be able to upload and download files as shown below.
<img width="1306" height="1016" alt="image" src="https://github.com/user-attachments/assets/66dd65c0-5e6f-4bb9-b7d1-bbe7762d59f6" />

If you are transferring very large files, we recommend transfer from another Globus endpoint (such as the Harvard Business School DTN, attached to the HBSGrid, or by creating your own endpoint using Globus Personal).

## Special Note on Uploading Files from the HBSGrid to the RCP Using Globus

As the HBSGrid prepares for retirement in FY27, we recommend creating RCP project spaces to replace projects currently hosted on the HBSGrid. For large data transfers from an HBSGrid project space to the RCP we recommend using Globus.

**1. Copy your HBSGrid project space folder or files to the Globus staging area**

Globus requires files to be staged in the `/export/globus` HBSGrid folder before they can be transferred to RCP, so you'll first need to copy your HBSGrid files there.

In NoMachine, open the file explorer and navigate to your project space folder. Select the folder you'd like to move to RCP, right click and select "Copy to."

<img width="474" height="358" alt="image" src="https://github.com/user-attachments/assets/f24b1d87-6d5e-4e29-a5cd-7f5dd531f326" />

<br></br>
Select the `/export/globus` folder as your destination, and then either create a new folder to house the data or click on an existing one.

<img width="343" height="368" alt="image" src="https://github.com/user-attachments/assets/4358b6c5-c76d-4e21-92b3-2663e580cd29" />

_Note: you can also move the data into the `/export/globus` staging area using Terminal commands (e.g., `cp -r /path/to/project-folder /export/globus/<your-folder-name>/`_

The files must be located in /export/globus/<your-folder-name> before you begin the Globus transfer.

**2. Open the HBS DTN collection in Globus**

Log in to Globus and navigate to the File Manager tab. In the Collection dialog box, search for and select the **Harvard Business School DTN Collection**. Click Transfer or Sync to…, then navigate to and select the folder containing your staged HBSGrid data.

<img width="971" height="242" alt="image" src="https://github.com/user-attachments/assets/a9d753e0-c76c-411b-a65e-fd29a1a5681c" />

**3. Connect to the RCP project space**

On the right-hand side of the screen, connect to your RCP project space. If you have not already done so, follow the instructions [above](syncfiles.md#using-globus): search for the **Harvard Business School S3 Storage** Collection, authenticate, and enter your AWS keys.

Navigate to or create the destination folder in your RCP project space where you would like the files to be transferred.

**4. Start the transfer**

Select the folder you wish to transfer and click on the Start arrow icon. For this workflow, files should transfer from the **Harvard Business School DTN collection** to the **Harvard Business School S3 Storage** collection.

<img width="909" height="155" alt="image" src="https://github.com/user-attachments/assets/1e4419e7-1fa6-4438-9c91-69fe2d1669af" />

**5. Verify the transfer**

Monitor the transfer status in Globus and confirm that the files appear in the expected RCP location. Do not delete the files from `/export/globus` until the transfer has completed successfully and the files have been verified.

If you need help at any point along the way, please contact [research@hbs.edu](mailto:research@hbs.edu).

## Managing Source Code - Syncing to Git

All launchers for IDEs (including Stata, VSCode, RStudio, Jupyter and Spyder) have git installed on their base images.   To use git for sessions using these launchers, please use the terminal window for each to execute git commands.  

For a list of common git commands see the [Git Hub Cheat Sheet](https://git-scm.com/cheat-sheet).

If you are brand new to code code version control with git, [please visit this useful guide](https://docs.github.com/en/get-started/start-your-journey).


If you are using Harvard’s Github enterprise for your repositories the standard login and password do not work and you will need to use either ssh keys or tokens.  Please see
1.	[https://github.com/settings/tokens](https://github.com/settings/tokens) for using tokens  
2.	https://github.com/settings/ssh for ssh

If you have any questions or run into issues, please reach out to [research@hbs.edu](research@hbs.edu).
