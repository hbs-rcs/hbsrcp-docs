# 📦 Project Spaces, Storage, and Available Software and Analysis Tools
## Project Spaces
Project owners can request new projects using this [form](https://secure.hbs.edu/accountManagement/secure/research-computing-platform/projectspace/new). To add additional team members to a project space, contact [research@hbs.edu](mailto:research@hbs.edu). Remember that you will not be able to request a project space or be added to an existing project until you have logged into the RCP at least once.

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
The RCP offers database capabilities through a back-end connection to [Amazon Aurora](https://aws.amazon.com/rds/aurora/). Connection parameters, including the username, password, and hostname can be obtained by clicking on the "Service Credentials" box that appears in the upper right hand side of the Workbench. Clicking on the box will reveal the connection parameters:

<img width="596" height="200" alt="image" src="https://github.com/user-attachments/assets/d414855f-4162-4aa7-9796-bc4719667df4" />

#### Connecting to an Existing Database
See below for sample code to connect to your database using Python. If you prefer to use R, please contact RCS for customized instructions.

##### Python

Using the [mysql](https://dev.mysql.com/doc/connector-python/en/connector-python-examples.html) python package:

```
import mysql.connector 
# Connect to the database 
conn = mysql.connector.connect( 
    user = 'username', 
    password = 'password'', 
    host = 'endpoint', 
    database = ''databasename')
```

#### DBeaver

DBeaver can be found on the [Utility Launcher](storage_software.md/#utility-launcher). After opening it, connect to an existing database by clicking on "Connect to a Database," select SQL, MySQL, and then Next.

<img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/60ab33c0-9187-4570-97e9-776de38adb3b" />
<br></br>

Using the information in the [Service Credentials](storage_software.md/#database) found on the Workbench tab, paste the Endpoint into the Server Host box, and replace the Username and Password with your service credentials. Click on the + SSH, SSL, tab and select SSL.

<img width="323" height="287" alt="image" src="https://github.com/user-attachments/assets/22e0f2cf-6e33-498c-bc6a-d8e5541b3de9" />
<br></br>

Unclick verify server certificate and click Finish.

<img width="322" height="289" alt="image" src="https://github.com/user-attachments/assets/3582ec75-f429-472a-a30e-17700d94bd76" />


#### Creating a New Database

!!! info inline end "Database Naming Requirements"
    
    Your database name must start with a letter, and can only consist of letters, numbers, or underscores!
There are several ways to create a new database from a DataFrame, which may have been loaded from various file formats (such as CSV or Parquet). Below is sample Python code demonstrating one approach.

##### Python

Using the [sqlalchemy](https://www.sqlalchemy.org/) python package:


```
from sqlalchemy import create_engine, text

# Define your Aurora cluster credentials and database name
AURORA_ENDPOINT = "endpoint" #The endpoint from the Service Credentials 
DB_USER = "username"
DB_PASSWORD = "password"
NEW_DB_NAME = "NewDatabase" #Database name of your choosing. Please note that the database name must start with a letter, and can only consist of letters, numbers, or underscores

try:
    # Create a SQLAlchemy engine
    engine = create_engine(f'mysql+pymysql://{DB_USER}:{DB_PASSWORD}@{AURORA_ENDPOINT}')

    # Create the database
    with engine.connect() as connection:
        connection.execute(text(f"CREATE DATABASE IF NOT EXISTS {NEW_DB_NAME}"))

    # Add the DataFrame to the database
    df.to_sql(name='my_table', con=engine, schema=NEW_DB_NAME, if_exists='replace', index=False)

except Exception as e:
    print(f"An error occurred: {e}")
```

## Available software and analysis tools

The RCP launchers feature the most commonly used research software and analysis tools, including *Rstudio*, *Spyder*, *VSCode*, and *Stata*. Additionally, if applicable for the software, each launcher is preloaded with commonly used packages and modules. 

### Installing Packages or Modules

!!! important inline end
     **Please note that the packages and modules you install are only available within a launcher, and not across the project's launchers**. If you terminate the launcher, these packages and modules will be deleted. 

If the package that you need to use is **not** preloaded, you can install it using the usual commands.

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

### Utility Launcher

The RCP features a Utility Launcher that makes it even easier to access commonly used desktop applications directly within your research environment. Use the Utility Launcher to quickly open tools such as:

* [LibreOffice](https://www.libreoffice.org/) for spreadsheets and documents
* File and database browsers like [DBeaver](https://dbeaver.io/)
* Data transfer tools like [FileZilla](https://filezilla-project.org/) and [rclone](https://rclone.org/)
* Additional desktop applications, without any local installation or setup

To see all available applications, first, click on the oval button in the upper left-hand side of the screen:<br></br>
<img width="140" height="59" alt="image" src="https://github.com/user-attachments/assets/699f36fa-9d72-4ed3-a19c-8ff59cf15627" />
<br></br>
Second, click on the app grid to reveal the installed applications:

<img width="607" height="323" alt="image" src="https://github.com/user-attachments/assets/3f672773-2164-4fd3-a147-36ef8b8b3418" />

## Running Background Jobs

A background job lets you start a computation and walk away; it keeps running on the server even after you close your browser, and the results are waiting for you when you come back. 

There are several ways to run background jobs on RCP, and selecting which to use depends on your use case. For small to medium jobs that can leverage the CPUs in a software's launcher for parallelization (if needed), you can run the background jobs in that launcher. For larger, more complex jobs that require a scheduler and/or extensive parallelization and resources, we recommend using the terminal provided in the [Parallel Computing Services (PCS)](storage_software.md#amazons-parallel-computing-services-pcs) launcher. 

### Research Software Launchers

Below, we provide detailed instructions and a video describing how to run long-running jobs in different launchers.

<details>
<summary>Jupyter</summary>

<h2>Overview</h2>

<p>This guide explains two ways to run long-running Python jobs in the background using JupyterLab on the HBS Research Computing Platform (RCP).</p>

<blockquote>
<p><strong>Important:</strong> JupyterLab behaves differently from RStudio and VSCode. When you reconnect to a notebook after closing the tab, the notebook cells will appear idle (showing <code>[ ]</code> instead of <code>[*]</code>). This is misleading — the kernel <strong>IS</strong> still running in the background. Always verify using the terminal command described in Step 3 of Method 1.</p>
</blockquote>

<iframe width="560" height="315" src="https://www.youtube.com/embed/AQ60-MvZtQk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<hr>

<h2>Methods at a Glance</h2>

<table>
<tr>
<th>Method 1: Run Notebook &amp; Close Tab</th>
<th>Method 2: Terminal with nohup</th>
</tr>
<tr>
<td>Run notebook cells, close the tab, and reconnect. The kernel continues running even though the notebook appears idle.<br><br>Verify progress via the terminal.</td>
<td>Open a Terminal from the Launcher and use <code>nohup</code> to run a Python script fully detached.<br><br><strong>Best for:</strong> jobs where you want live monitoring and full stop/start control.</td>
</tr>
</table>

<hr>

<h2>Method 1: Run in Notebook &amp; Close the Tab</h2>

<h3>Step 1 — Open a New Notebook</h3>

<p>In JupyterLab, click the <strong>+</strong> button or go to <strong>File &gt; New Launcher</strong>. Under the <strong>Notebook</strong> section, click <strong>Python 3 (ipykernel)</strong> to create a new notebook.</p>

<h3>Step 2 — Paste and Run the Script</h3>

<p>In the first cell, paste your code. This example is called <code>video_test.py</code>:</p>

<pre><code class="language-python">import time
from datetime import datetime

with open("notebook_test.log", "w") as f:
    for i in range(60):
        msg = f"{datetime.now():%H:%M:%S} - Step {i+1} - still running"
        print(msg)
        f.write(msg + "\n")
        f.flush()
        time.sleep(5)

print("Done!")
</code></pre>

<p>Click the <strong>Run</strong> button (or press <strong>Shift+Enter</strong>) to execute the cell. You will see timestamped output appearing in the cell output area. The script also writes progress to a log file in your home directory.</p>

<h3>Step 3 — Close the Browser Tab</h3>

<p>While the cell is still running (shown by <code>[*]</code> next to it), close the JupyterLab browser tab. The kernel will continue executing in the background.</p>

<h3>Step 4 — Reconnect and Verify</h3>

<p>Return to the HBS RCP and click <strong>Connect</strong> on your JupyterLab session. Open your notebook. You may notice that the cell now shows <code>[ ]</code> (empty brackets) instead of <code>[*]</code> — this indicates that the notebook's display has disconnected from the kernel output.</p>

<blockquote>
<p><strong>The notebook appearing idle does NOT mean the job has stopped.</strong> The kernel continues running on the server.</p>
</blockquote>

<p>To confirm the job is still running, open a new <strong>Terminal</strong> from the Launcher and run:</p>

<pre><code class="language-bash">tail -f /your/home/directory/your_file_name.log
</code></pre>

<p>You should see new timestamped lines appearing, proving the notebook is still executing. Press <strong>Ctrl+C</strong> to stop watching the log.</p>

<hr>

<h2>Method 2: Terminal with nohup</h2>

<h3>Step 1 — Open a Terminal from the Launcher</h3>

<p>In JupyterLab, open the Launcher (click the <strong>+</strong> button or <strong>File &gt; New Launcher</strong>). Scroll down to the <strong>Other</strong> section and click the <strong>Terminal</strong> tile. A bash shell will open in a new tab.</p>

<h3>Step 2 — Launch the Background Job</h3>

<p>In the terminal, run:</p>

<pre><code class="language-bash">nohup python your_file_name.py &gt; output.log 2&gt;&amp;1 &amp;
</code></pre>

<p><strong>What each part means:</strong></p>

<table>
<tr>
<th>Part</th>
<th>Description</th>
</tr>
<tr>
<td><code>nohup</code></td>
<td>Keeps the job running after logout</td>
</tr>
<tr>
<td><code>python your_file_name.py</code></td>
<td>Runs your Python script</td>
</tr>
<tr>
<td><code>&gt; output.log</code></td>
<td>Captures all printed output</td>
</tr>
<tr>
<td><code>2&gt;&amp;1</code></td>
<td>Also captures errors</td>
</tr>
<tr>
<td><code>&amp;</code></td>
<td>Runs the process in the background</td>
</tr>
</table>

<p>A process ID will appear (e.g., <code>[1] 18079</code>). Note this number. You can now close the browser tab — the job continues running.</p>

<h3>Step 3 — Monitor Job Progress</h3>

<pre><code class="language-bash">tail -f output.log
</code></pre>

<p>New lines appear in real time. Press <strong>Ctrl+C</strong> to stop watching without stopping the job.</p>

<h3>Step 4 — Check Whether the Job is Still Running</h3>

<pre><code class="language-bash">jobs
</code></pre>

<p>You will see:</p>

<pre><code>[1]+  Running    nohup python your_file_name.py &gt; output.log 2&gt;&amp;1 &amp;
</code></pre>

<hr>

<h2>Stopping a Background Job</h2>

<p>Run these commands in the JupyterLab terminal.</p>

<h3>Method A — Kill by Job Number</h3>

<pre><code class="language-bash">kill 18079
</code></pre>

<p>Replace <code>18079</code> with the job number shown when you launched the job.</p>

<h3>Method B — Kill by Process ID</h3>

<pre><code class="language-bash">kill %1
</code></pre>

<h3>Method C — Kill by Script Name</h3>

<pre><code class="language-bash">pkill -f video_test.py
</code></pre>

<hr>

<h2>Best Practices</h2>

<ul>
<li>Test on a small sample before launching a full run.</li>
<li>Use log files to monitor progress and catch errors.</li>
<li>Remember: a notebook showing <code>[ ]</code> does <strong>not</strong> mean the job has stopped — always verify with <code>tail -f</code>.</li>
<li>Confirm your script writes files to the expected paths before starting.</li>
</ul>

<hr>

<h2>Getting Help</h2>

<p>If you run into any issues with background jobs or anything else on the RCP, the HBS Research Computing team is here to help.</p>

<p>📧 <strong>Email:</strong> <a href="mailto:research@hbs.edu">research@hbs.edu</a></p>

</details>

<details>

<summary>RStudio</summary>

<h2>Overview</h2>

<p>This guide explains two ways to run long-running R jobs in the background using RStudio on the HBS Research Computing Platform (RCP).</p>

<iframe width="560" height="315" src="https://www.youtube.com/embed/BjQMP3xFh3w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<hr>

<h2>Methods at a Glance</h2>

<table>
<tr>
<th>Method 1: Close the Browser Tab</th>
<th>Method 2: Terminal with nohup</th>
</tr>
<tr>
<td>Run your script in the RStudio console, then close the tab. The session keeps running. When you reconnect, your output will be waiting.<br><br><strong>Best for:</strong> simple scripts you want to kick off quickly.</td>
<td>Use RStudio's built-in Terminal with the <code>nohup</code> command to launch a script that runs fully detached from the browser session.<br><br><strong>Best for:</strong> long jobs where you want monitoring and control.</td>
</tr>
</table>

<hr>

<h2>Method 1: Close the Browser Tab</h2>

<h3>Step 1 — Create and Save a Test Script</h3>

<p>Open RStudio and create a new R script. This example script named <code>video_test.R</code> simulates a long-running analysis by printing a status message every 5 seconds for 60 iterations (5 minutes total).</p>

<pre><code class="language-r">for (i in 1:60) {
  print(paste("Step", i, "- still running"))
  Sys.sleep(5)
}
print("Done!")
</code></pre>

<h3>Step 2 — Run the Script</h3>

<p>With your script open, click the <strong>Run</strong> button in RStudio (or press <strong>Ctrl+Enter</strong> / <strong>Cmd+Enter</strong>) to execute the code. You will see output appearing in the Console panel:</p>

<pre><code>[1] "Step 1 - still running"
[1] "Step 2 - still running"
...
</code></pre>

<h3>Step 3 — Close the Browser Tab</h3>

<p>Once the script is running, close the RStudio browser tab. The R session will continue running on the server in the background.</p>

<h3>Step 4 — Reconnect and View Results</h3>

<p>Navigate back to the HBS RCP and click <strong>Connect</strong> on your RStudio session. Scroll through the Console output to confirm the script continued running while the tab was closed.</p>

<hr>

<h2>Method 2: Terminal with nohup</h2>

<h3>Step 1 — Open the Terminal</h3>

<p>In RStudio, click the <strong>Terminal</strong> tab at the bottom of the screen (next to the Console tab). A bash shell connected to the server will open.</p>

<h3>Step 2 — Launch the Background Job</h3>

<p>In the Terminal, run the following command and press Enter:</p>

<pre><code class="language-bash">nohup Rscript your_file_name.R &gt; output.log 2&gt;&amp;1 &amp;
</code></pre>

<p><strong>What each part means:</strong></p>

<table>
<tr>
<th>Part</th>
<th>Description</th>
</tr>
<tr>
<td><code>nohup</code></td>
<td>Keeps the job running after you log out or close the browser</td>
</tr>
<tr>
<td><code>Rscript your_file_name.R</code></td>
<td>Runs your R script from the command line</td>
</tr>
<tr>
<td><code>&gt; output.log</code></td>
<td>Redirects all printed output to a log file</td>
</tr>
<tr>
<td><code>2&gt;&amp;1</code></td>
<td>Also captures error messages in the same log</td>
</tr>
<tr>
<td><code>&amp;</code></td>
<td>Sends the process to the background immediately</td>
</tr>
</table>

<p>After pressing Enter, a process ID (PID) and job number will appear, for example:</p>

<pre><code>[1] 17942
</code></pre>

<p>This number is your job identifier. Note it down in case you need to stop the job later. You can now close the browser tab — the job will keep running.</p>

<h3>Step 3 — Monitor Job Progress</h3>

<p>To see the live output of your running job, reopen RStudio, go to the Terminal, and type:</p>

<pre><code class="language-bash">tail -f output.log
</code></pre>

<p>New lines will appear in real time as Rscript runs. Press <strong>Ctrl+C</strong> to stop watching the log — this does <strong>NOT</strong> stop the job itself.</p>

<h3>Step 4 — Check Whether the Job is Still Running</h3>

<p>To verify the job is running in the background, type:</p>

<pre><code class="language-bash">jobs
</code></pre>

<p>You will see output like:</p>

<pre><code>[1]+  Running    nohup Rscript your_file_name.R &gt; output.log 2&gt;&amp;1 &amp;
</code></pre>

<hr>

<h2>Stopping a Background Job</h2>

<p>If you discover a bug or need to cancel the job, there are three methods. All are run in the Terminal.</p>

<h3>Method A — Kill by Job Number</h3>

<pre><code class="language-bash">kill 17942
</code></pre>

<p>Replace <code>17942</code> with the job number that was shown when you launched the job.</p>

<h3>Method B — Kill by Process ID</h3>

<pre><code class="language-bash">kill %1
</code></pre>

<h3>Method C — Kill by Script Name</h3>

<pre><code class="language-bash">pkill -f your_file_name.R
</code></pre>

<p>Useful if you have lost track of the job number or PID.</p>

<p>In all cases, confirm termination by running <code>jobs</code> again — you should see <code>Terminated</code> next to the job.</p>

<hr>

<h2>Best Practices</h2>

<ul>
<li>Test your script on a small sample before launching a full long-running job.</li>
<li>Validate that outputs look correct on a subset before scaling up.</li>
<li>Monitor <code>output.log</code> regularly with <code>tail -f</code> to catch errors early.</li>
<li>Confirm that your script writes output files to the expected paths before starting.</li>
<li>Save your script before running — unsaved edits will not be picked up.</li>
</ul>

<hr>

<h2>Getting Help</h2>

<p>If you run into any issues with background jobs or anything else on the RCP, the HBS Research Computing team is here to help.</p>

<p>📧 <strong>Email:</strong> <a href="mailto:research@hbs.edu">research@hbs.edu</a></p>

</details>

<details>

<summary>Stata</summary>

<h2>Overview</h2>

<p>This guide explains two ways to run long-running Stata do-files in the background on the HBS Research Computing Platform (RCP).</p>

<iframe width="560" height="315" src="https://www.youtube.com/embed/43Kzsl1O8QU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<hr>

<h2>Methods at a Glance</h2>

<table>
<tr>
<th>Method 1: Close the Browser Tab</th>
<th>Method 2: Terminal with nohup</th>
</tr>
<tr>
<td>Run your do-file from the Stata console, then close the browser tab. The session keeps running.<br><br><strong>Best for:</strong> quick kick-off with no extra commands.</td>
<td>Open a Terminal via the Stata desktop app grid and use <code>nohup stata -b do</code> to run the do-file fully detached.<br><br><strong>Best for:</strong> long jobs where you want monitoring and control.</td>
</tr>
</table>

<hr>

<h2>Method 1: Close the Browser Tab</h2>

<h3>Step 1 — Create and Save a Test Do-File</h3>

<p>Open Stata, create a new do-file, and paste your code inside. This example code called <code>video_test.do</code> displays a message every 5 seconds (5000 milliseconds) for 60 iterations.</p>

<pre><code class="language-stata">forvalues i = 1/60 {
    display "Step `i' - still running"
    sleep 5000
}
</code></pre>

<h3>Step 2 — Run the Do-File</h3>

<p>You will see output appearing in the Results window:</p>

<pre><code>Step 1 - still running
Step 2 - still running
...
</code></pre>

<h3>Step 3 — Close the Browser Tab</h3>

<p>While the do-file is still running, close the Stata browser tab. The Stata session will continue running on the server in the background.</p>

<h3>Step 4 — Reconnect and View Results</h3>

<p>Return to the HBS RCP and click <strong>Connect</strong> on your Stata session. The Results window will show output produced while the tab was closed.</p>

<hr>

<h2>Method 2: Terminal with nohup</h2>

<h3>Step 1 — Open Terminal</h3>

<p>Stata on RCP runs inside a Linux desktop environment. To open a terminal, follow these two steps:</p>

<ol>
<li>Click the <strong>oval/grid button</strong> in the top-left corner of the Stata desktop to open the application menu.</li>
<li>In the app grid, find and click the <strong>Terminal</strong> icon to open a bash shell window.</li>
</ol>

<h3>Step 2 — Launch the Background Job</h3>

<p>In the terminal, run the following command and press Enter:</p>

<pre><code class="language-bash">nohup stata -b do your_file_name.do &gt; output.log 2&gt;&amp;1 &amp;
</code></pre>

<p><strong>What each part means:</strong></p>

<table>
<tr>
<th>Part</th>
<th>Description</th>
</tr>
<tr>
<td><code>nohup</code></td>
<td>Keeps the job running after logout or browser close</td>
</tr>
<tr>
<td><code>stata -b do</code></td>
<td>Runs Stata in batch (non-interactive) mode, executing a do-file</td>
</tr>
<tr>
<td><code>your_file_name.do</code></td>
<td>The do-file to run</td>
</tr>
<tr>
<td><code>&gt; output.log</code></td>
<td>Redirects console output to a log file</td>
</tr>
<tr>
<td><code>2&gt;&amp;1</code></td>
<td>Also captures error messages</td>
</tr>
<tr>
<td><code>&amp;</code></td>
<td>Runs the process in the background</td>
</tr>
</table>

<p>A process ID and job number will appear (e.g., <code>[1] 21449</code>). Note this number. You can now close the browser tab — the job continues running.</p>

<blockquote>
<p><strong>Note:</strong> Stata batch mode also automatically creates a <code>.log</code> file matching your do-file name (e.g., <code>video_test.log</code>) in the current directory. This log captures the full Stata output including all displayed results.</p>
</blockquote>

<h3>Step 3 — Monitor Job Progress</h3>

<p>To watch the live output from your Stata job, reopen the terminal and run:</p>

<pre><code class="language-bash">tail -f your_file_name.log
</code></pre>

<p>New lines will appear in real time as Stata runs. Press <strong>Ctrl+C</strong> to stop watching the log — this does <strong>NOT</strong> stop the job itself.</p>

<h3>Step 4 — Check Whether the Job is Still Running</h3>

<pre><code class="language-bash">jobs
</code></pre>

<p>You will see output like:</p>

<pre><code>[1]+  Running    nohup stata -b do your_file_name.do &gt; output.log 2&gt;&amp;1 &amp;
</code></pre>

<hr>

<h2>Stopping a Background Job</h2>

<p>Run these commands in the terminal. If you noted the process ID and job number previously, you can use the first two methods.</p>

<h3>Method A — Kill by Job Number</h3>

<pre><code class="language-bash">kill 21449
</code></pre>

<p>Replace <code>21449</code> with the job number that was shown when you launched the job.</p>

<h3>Method B — Kill by Process ID</h3>

<pre><code class="language-bash">kill %1
</code></pre>

<h3>Method C — Kill by Do-File Name</h3>

<pre><code class="language-bash">pkill -f video_test.do
</code></pre>

<p>Useful if you have lost track of the job number or PID. Replace <code>video_test.do</code> with the name of your do-file.</p>

<p>In all cases, confirm termination by running <code>jobs</code> again — you should see <code>Terminated</code> next to the job.</p>

<hr>

<h2>Best Practices</h2>

<ul>
<li>Test your do-file on a small sample before launching a full long-running job.</li>
<li>Validate that outputs look correct on a subset before scaling up.</li>
<li>Monitor your log file with <code>tail -f</code> to catch errors early.</li>
<li>Confirm that your do-file writes datasets to the expected paths before starting.</li>
<li>Save your do-file before running — unsaved edits will not be picked up.</li>
</ul>

<hr>

<h2>Getting Help</h2>

<p>If you run into any issues with background jobs or anything else on the RCP, the HBS Research Computing team is here to help.</p>

<p>📧 <strong>Email:</strong> <a href="mailto:research@hbs.edu">research@hbs.edu</a></p>

</details>

<details>
<summary>VSCode</summary>

<h2>Overview</h2>

<p>This guide explains two ways to run long-running Python jobs in the background using VSCode on the HBS Research Computing Platform (RCP).</p>

<iframe width="560" height="315" src="https://www.youtube.com/embed/O1TMGFwOKpw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<hr>

<h2>Methods at a Glance</h2>

<table>
<tr>
<th>Method 1: Close the Browser Tab</th>
<th>Method 2: Terminal with nohup</th>
</tr>
<tr>
<td>Run your script using the VSCode play button, then close the tab. The session keeps running.<br><br><strong>Best for:</strong> quick kick-off with no extra commands.</td>
<td>Open a bash terminal in VSCode and use <code>nohup</code> to run the script fully detached.<br><br><strong>Best for:</strong> long jobs where you want monitoring and control.</td>
</tr>
</table>

<hr>

<h2>Method 1: Close the Browser Tab</h2>

<h3>Step 1 — Create and Save a Test Script</h3>

<p>Open VSCode and create a new file. This example code is called <code>video_testing.py</code>:</p>

<pre><code class="language-python">import time

for i in range(60):
    print(f"Step {i+1} - still running", flush=True)
    time.sleep(5)

print("Done!")
</code></pre>

<h3>Step 2 — Run the Script</h3>

<p>Click the <strong>play button</strong> (triangle) in the top-right corner of the editor. Output will appear in the Terminal panel at the bottom.</p>

<h3>Step 3 — Stop an Interactive Job (if needed)</h3>

<p>To stop a script that is currently running interactively, click the <strong>trash icon</strong> next to the Python terminal entry in the terminal panel.</p>

<h3>Step 4 — Close the Browser Tab</h3>

<p>Once the script is running, close the VSCode browser tab. The Python process continues on the server.</p>

<h3>Step 5 — Reconnect and View Results</h3>

<p>Return to the HBS RCP and click <strong>Connect</strong> on your VSCode session. The terminal will reconnect and show any output produced while you were away.</p>

<hr>

<h2>Method 2: Terminal with nohup</h2>

<h3>Step 1 — Open a Bash Terminal</h3>

<p>The <code>nohup</code> command must be run in a bash terminal — not the Python terminal used for interactive runs. Click the <strong>+</strong> dropdown in the Terminal panel and select <strong>bash</strong> to open a new bash shell.</p>

<h3>Step 2 — Launch the Background Job</h3>

<p>In the bash terminal, run:</p>

<pre><code class="language-bash">nohup python your_file_name.py &gt; output.log 2&gt;&amp;1 &amp;
</code></pre>

<p><strong>What each part means:</strong></p>

<table>
<tr>
<th>Part</th>
<th>Description</th>
</tr>
<tr>
<td><code>nohup</code></td>
<td>Keeps the job running after logout</td>
</tr>
<tr>
<td><code>python your_file_name.py</code></td>
<td>Runs your Python script</td>
</tr>
<tr>
<td><code>&gt; output.log</code></td>
<td>Redirects printed output to a log file</td>
</tr>
<tr>
<td><code>2&gt;&amp;1</code></td>
<td>Also captures errors in the same file</td>
</tr>
<tr>
<td><code>&amp;</code></td>
<td>Sends the process to the background</td>
</tr>
</table>

<p>A process number and job ID will appear (e.g., <code>[1] 41386</code>). Note this number. You can now close the browser — the job will continue running.</p>

<h3>Step 3 — Monitor Job Progress</h3>

<pre><code class="language-bash">tail -f output.log
</code></pre>

<p>New lines appear in real time. Press <strong>Ctrl+C</strong> to stop watching without stopping the job.</p>

<h3>Step 4 — Check Whether the Job is Still Running</h3>

<pre><code class="language-bash">jobs
</code></pre>

<p>You will see output like:</p>

<pre><code>[1]+  Running    nohup python your_file_name.py &gt; output.log 2&gt;&amp;1 &amp;
</code></pre>

<hr>

<h2>Stopping a Background Job</h2>

<p>Run these commands in the bash terminal.</p>

<h3>Method A — Kill by Job Number</h3>

<pre><code class="language-bash">kill 41386
</code></pre>

<p>Replace <code>41386</code> with the PID shown when you launched the job.</p>

<h3>Method B — Kill by Process ID</h3>

<pre><code class="language-bash">kill %1
</code></pre>

<h3>Method C — Kill by Script Name</h3>

<pre><code class="language-bash">pkill -f your_file_name.py
</code></pre>

<p>Useful when you have lost track of the process ID or job number.</p>

<hr>

<h2>Best Practices</h2>

<ul>
<li>Test on a small sample before launching a full run.</li>
<li>Validate output on a subset before scaling up.</li>
<li>Monitor <code>output.log</code> regularly with <code>tail -f</code>.</li>
<li>Confirm your script writes files to the expected paths before starting.</li>
</ul>

<hr>

<h2>Getting Help</h2>

<p>If you run into any issues with background jobs or anything else on the RCP, the HBS Research Computing team is here to help.</p>

<p>📧 <strong>Email:</strong> <a href="mailto:research@hbs.edu">research@hbs.edu</a></p>

</details>

### Amazon's Parallel Computing Services (PCS)

> ⚠️ **Important:** To use PCS, please ensure that the project owner has [enabled the EFS service and the PCS launcher](manageprojects.md/#configure-services). The first time you launch PCS, it will take about 15 minutes to provision.

Amazon [PCS (Parallel Computing Service)](https://docs.aws.amazon.com/pcs/latest/userguide/what-is-service.html) is a fully managed service that gives you access to a large cluster of computers in the cloud. The service allows you to submit computational jobs using a submission script that run across hundreds or thousands of CPUs simultaneously thus dramatically reducing the time it takes to complete large or complex analyses. You only pay for the computing time you actually use, and Amazon handles all the underlying infrastructure for you. 

**Note:** AWS uses [SLURM](https://slurm.schedmd.com/quickstart.html) submission scripts (versus the LSF scheduler on the HBSGrid). If you are moving from the HBSGrid to RCP please note that your batch submission scripts will need to be altered slightly.

#### Accessing the PCS Launcher

Activate a PCS session and connect to it. Once the browser is connected, click on the oval in the upper left hand corner, then select the Grid app at the bottom of the screen, then the Terminal:

<img width="576" height="448" alt="image" src="https://github.com/user-attachments/assets/28ba27f2-c4cd-4be1-ac63-baced5397b3f" />

#### Understanding PCS Storage Options

**To take full advantage of the high-performant storage in the PCS launcher (EFS and Lustre), please copy or move relevant files (code/data) from your S3 bucket to the PCS storage system** (see instructions below). While you can technically work from files in your S3 bucket, you will not take advantage of the full power of the PCS system, and unexpected errors may arise as you cannot write streaming error or output files to the S3 bucket.

For single-node, single-stream work, we recommend using the EFS volume. When you log into PCS and open a new Terminal this is the default folder. If you would like to create a new folder within it, you can use the `mkdir NEWFOLDERNAME` command.

**Note: the `home` directory is visible to all users in the project folder.**

```
cd home/ec2-user/NEWFOLDERNAME
```
For parallel, multi-node work, we recommend using the Lustre volume. If you would like to create a new folder within it, you can use the `mkdir NEWFOLDERNAME` command.

```
cd shared/NEWFOLDERNAME
```

To facilitate copying or moving files from your S3 bucket to either of these volumes, the `studies` folder is visible from the PCS launcher here:

```
cd mnt/studies/yourprojectspacename
```
##### Moving/Copying Files from S3 to PCS Storage

Below is sample code to move relevant files from your project's S3 storage to the EFS storage system.

```
placholder, get sample code from Paul
```

#### Running a Single-Node Job

Please note that the instructions below assume you have already moved your relevant files into the PCS storage system. 

**1\. Open the terminal and navigate to the folder on the EFS volume where your jobs scripts and outputs will be stored.**

For single-node jobs, we recommend using the EFS storage in the `/home/ec2-user` directory:
```
cd home/ec2-user/yourfolder
```

**2\. Identify and store the partition name**

In the Terminal, run this command to store the name of the partition you are working on. This will be used in the next step and is necessary to run the job.
    
```
PARTITION=$(sinfo -h -o "%P" | grep ondemand | tr -d '*')
```
   
**3\. Create a SLURM Job Script**

The example below is a simple SLURM job script that runs on a single node and writes output and error logs to files in your project space. While the SBATCH commands will depend on your use        case, **you must always include the `#SBATCH --partition=${PARTITION}` command to ensure that the job runs on the correct partition**. 

```
cat << EOF > job.sh
#!/bin/bash
#SBATCH -J single
#SBATCH -o /mnt/studies/RCS_Project-Storage-mf9/RCP_Testing/single.%j.out
#SBATCH -e /mnt/studies/RCS_Project-Storage-mf9/RCP_Testing/single.%j.err

echo "This is job \${SLURM_JOB_NAME} [\${SLURM_JOB_ID}] running on \${SLURMD_NODENAME}, submitted from \${SLURM_SUBMIT_HOST}" && sleep 60 && echo "Job complete"
EOF
```

Below is a quick overview of the components of the bash script above, but please see the [SLURM](https://slurm.schedmd.com/documentation.html) documentation for additional detail.

| Component | What It Is | What It Does |
|---|---|---|
| `cat << EOF > job.sh` / `EOF` | Heredoc marker | Creates `job.sh` and writes everything between the two `EOF` markers into it — the closing `EOF` signals where the file content ends |
| `#!/bin/bash` | Shebang line | Tells the system to run this script using the Bash shell — must always be the first line |
| `#SBATCH -J single` | SLURM directive | Sets the **job name** to `single` — this is what your job will be called in the queue |
| `#SBATCH -o` / `-e` | SLURM directive | Sets the **output** (`-o`) and **error** (`-e`) log files — `%j` is replaced with the job ID at runtime (e.g. `single.12345.out` / `single.12345.err`) |
| `#SBATCH --partition=${PARTITION}` | SLURM directive | Sets the **partition** the job will run on — `${PARTITION}` is replaced with the partition name captured dynamically before the script was created (e.g. `--partition=ondemand`) |
| `echo ... && sleep 60 && echo "Job complete"` | Job body | Prints job details on start, waits **60 seconds** to simulate work, then prints a completion message — `&&` ensures each command only runs if the previous one succeeded |
| `${SLURM_JOB_NAME}` `${SLURM_JOB_ID}` `${SLURMD_NODENAME}` `${SLURM_SUBMIT_HOST}` | SLURM variables | Automatically populated by SLURM at runtime — prints the job **name**, **ID**, **compute node**, and **submit host** inside the echo message |
 
**4\. Submit the Job to SLURM**
Submit the job script to the SLURM scheduler.

```
sbatch --partition=$PARTITION job.sh
```
<img width="461" height="38" alt="image" src="https://github.com/user-attachments/assets/0c31df9b-9899-4926-a66b-e4835f21a48f" />

**5\. Monitor Job Status**

Use the job ID returned by `sbatch` to monitor the job using the `squeue` command.

```
squeue --job <job-id>
```

Example:
```
squeue --job 1
```
Continue checking until the job reaches the R (running) state.
   
<img width="461" height="38" alt="image" src="https://github.com/user-attachments/assets/bbf79322-06af-434a-9341-9d6ed4af92ca" />

The job is complete when `squeue` no longer returns any output for the job ID.

<img width="461" height="38" alt="image" src="https://github.com/user-attachments/assets/beb812b4-95ea-425b-bb62-cc8d331c8f62" />

**6\. Review Job Output Files**

Once the job completes, inspect the contents of your project space to view the generated output and error files. Confirm the location of the files:

```
ls
```

View the contents of your output file:

```
cat output.log
```

   
   
