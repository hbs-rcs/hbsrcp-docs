# 📝 Changelog

## 4/16/25: Version 1.0.0.502
### New Features
- Project Status: Project Owners can now switch a project’s status between 
Active and Dormant as needed. 
    - In the **Active** state, your project, launchers, and associated files are fully accessible and ready to use. 
    - In the **Dormant** state, the project and its resources are temporarily disabled and unavailable—until the status is changed back to Active. 

This new functionality helps you manage project activity and resources more effectively and reduce clutter when a project is not in use. 

### Improvements
- Improved Stata and Jupyter Performance: Stata and Jupyter are now powered by an AMI, reducing launcher load time by up to 50%. 

*Note: Active sessions initiated prior this release will need to be restarted for the changes to take effect.*

## 4/2/25: Patch Release
### Improvements
- Improved VS Code Performance: We are transitioning from a container-based launcher to one based on AMI. This change reduces launcher load times by up to 50%.

- GPU Support for VSCode: VSCode now supports access to GPU resources on the cloud, allowing users to access 1, 2, or 4 GPUs per session.

*Note: Active sessions initiated prior this release will need to be restarted for the changes to take effect.*

## 3/18/25: Version 1.0.0.440
### Improvements 

- Improved Spyder permformance: Faster startup time for Spyder Launcher sessions due to new AMI based configurations.
  
  *Note: Active sessions initiated prior this release will need to be restarted for the changes to take effect.*

### Bug Fixes 

- Files up to 5GB can now be uploaded directly to the platform.

