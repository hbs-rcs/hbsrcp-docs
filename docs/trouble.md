# Troubleshooting

## GPU Provisioning "Fails"

<img width="1510" height="576" alt="image" src="https://github.com/user-attachments/assets/b0e7c108-cb5f-4225-90aa-445fcd828009" />

GPU instances are occasionally unavailable due to limited capacity in AWS regions. If your session shows a **Failed** status, terminate it and try launching a new session with a similar configuration, or wait a few minutes and try again — availability often changes quickly. To add additional configurations to your launchers, please see our documentation [here](manageprojects.md#modify-services). 

## Globus Folders Appear as 0-Byte Files
Directories created via Globus may initially appear as 0-byte files. This happens because folders transferred through Globus are stored in Amazon S3 (your project space) with the content type `application/x-globus-dir-placeholder`, which S3 treats as a file rather than a directory. After transferring folders through Globus, open each folder once from the RCP Files tab so its content type is updated and recognized as a directory, or, if using an active utility session, restart the session.
