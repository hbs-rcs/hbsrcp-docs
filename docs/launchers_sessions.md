# 🐚 Starting Launchers and Running Sessions
## Selecting and Starting Launchers
Click on your project and select one of the available **launchers** to create a new **session**. Note that each launcher has multiple configurations of CPUs/GPUs and memory, and that these vary by [software](storage_software.md#available-software).
<img width="932" height="245" alt="image" src="https://github.com/user-attachments/assets/9df0bebc-9f24-4562-9b83-acfd03d62bd2" />

Select your software, name the session, and choose the CPU/GPU and memory allocation (see our [guidance on choosing resoures](launchers_sessions.md#guidance-on-choosing-resources)) that is most appropriate for your work. Keep in mind that there are different [costs](billing.md#active-projects) associated with each configuration. **Starting a launcher for the first time can take 5-10 minutes.**

<img width="368" height="335" alt="image" src="https://github.com/user-attachments/assets/35ca678b-9f37-4c74-a731-76be37e43a13" />

Once your session has been provisioned, click on "Connect" to open the software in your browser. 

<img width="296" height="191" alt="image" src="https://github.com/user-attachments/assets/d9296a23-7138-42fb-a31f-5c310a2d333e" />

### Starting Sessions
Once a launcher is provisioned, it will appear as one of your sessions at the top of your project space Workbench when you log into the RCP. Click on the "Start" button to re-start the session. It will take a few minutes to load, and then the "Connect" button will appear. Click on the "Connect" button to open the software in your browser.

<img width="293" height="188" alt="image" src="https://github.com/user-attachments/assets/95515c60-5bc0-4bb8-a778-02f38dfd6067" /><br>

<img width="296" height="191" alt="image" src="https://github.com/user-attachments/assets/097e17f8-82d2-4987-a73d-6a7d042c9e33" />

### Stopping Sessions
If you have finished with your session, but plan to return to it, please ensure you have **stopped** it. The Stop option will appear after clicking on the hamburger menu to the right of the Connect button. Keeping the session running, even when you’re not actively using it, will incur charges, whereas a stopped session only incurs minor storage costs.

<img width="225" height="155" alt="image" src="https://github.com/user-attachments/assets/f355f2bd-7f5c-4fc7-8112-3466b635d68a" />

### Terminating Launchers
If you anticipate no longer needing a launcher, please **terminate** it. The Terminate option will appear after clicking on the hamburger menu to the right of the Start button of a stopped session. A terminated launcher will incur no costs. Keep in mind that once you terminate a launcher, downloaded packages (e.g., R packages) will be removed and unavailable for future use (i.e., if you restart a launcher you will need to recreate your environment).


<img width="233" height="141" alt="image" src="https://github.com/user-attachments/assets/c1f3978d-934e-4566-adb0-f73a5131b3d7" />

## Guidance on Choosing Resources
### Memory (RAM)

Specific memory requirements depend on the nature of the job, but as a rough guide we recommend requesting RAM 4-10 times the size of your data. For example, if you have a 6 Gb.csv file you may wish to request 24GB of memory or so.


Quick Tips for Choosing RAM:

If your code runs on your local machine, start by asking for the same amount of RAM or less (for example, if your laptop has 8GB of RAM, try asking for 8GB).
If you are loading in native binary data files, ask for an amount of RAM about 1.5x the size of your data.
If you are importing a text file (e.g., .csv), you may need to request up to 10x the size of the text file. We discourage ongoing reading and writing of text files; to save time and RAM, try to read your text files into binary data files and work primarily with those.
You can review your memory usage from a past job by running bhist -l JOBID (use bhist alone for a list of your recently run jobs). Take note of MAX MEM and when you run a similar job in the future, request that amount plus about 20% for wiggle room (e.g., if your past job had a maximum memory usage of 10GB, request 12GB next time).
### CPU/GPUs
A GPU (graphics processing unit) is a processor that is great at handling specialized computations. We can contrast this to the Central Processing Unit (CPU), which is great at handling general computations. CPUs power most of the computations performed on the devices we use daily.

GPU can be faster at completing tasks than CPU. However, it is not true for every case. The performance hugely depends on the type of computation being performed. GPUs are great at tasks that can be run in parallel ....and are often used for Machine Learning types of'embarrassingly parallel' tasks (== a huge task can be broken down into many smaller ones that are completely independent of one another).

-- Taken and adapted from Why Deep Learning Uses GPUs


Request only 1 CPU unless you know that you are using code or libraries that were written to run in parallel. 


We recommend that you request only 1 CPU unless you know that you are using code or libraries that were written to run in parallel such as Matlab parallel processint toolbox, Python multiprocessing library, or the R future package. For detailed parallel processing instructons refer to our tutorial.
