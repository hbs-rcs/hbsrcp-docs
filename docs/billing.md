# Costs and Billing

We have developed a cloud cost chargeback model with the following principles:
    - Positive experience for faculty to use the platform and to experiment 
    - Reasonable and clear to faculty 
    - Incentive to use resources wisely 
    - Controls to monitor and manage costs, including faculty-level AWS subaccounts 
        and code optimization in partnership with RCS and IT Research Technologies 
    - Alignment with the research budget planning process 

During the initial rollout, all cloud costs incurred on the platform will be covered through an automatic reimbursement process. After the initial rollout, cloud costs incurred on the platform will be covered through an automatic reimbursement process up to a limit, set to cover most faculty and usage. Costs above the limit will be charged to research budgets, with increases to budgets as needed through the research budget supplement request process. We will gather data on cloud costs and usage to validate our budget assumptions. 

Project owners can [view accrued costs for their projects within the platform](manageprojects.md#view-costs).

## Storage Costs 

Costs for the RCP are dictated by Amazon Web Services (AWS), which sets rates based on storage type. The RCP has two types of storage, both charged in increments of gigabytes:
    - Project storage using Amazon S3 buckets 
    - Storage associated with each launcher (i.e., local storage for each virtual machine) using Amazon’s Elastic File System (EFS). 

### Active Projects 

Active projects incur project storage and launcher costs. The cost of running launcher sessions will vary based on the configuration selected. A stopped launcher will incur minor costs (due to storage). Both costs will be posted shortly. There is no cost for unlaunched launchers. You can associate as many launchers with a project as you’d like and will only incur costs when a session is created.  

### Dormant and Archived Projects 

Dormant and archived project costs will be for storage only. Dormant project storage rates are similar to active ones, but with no EFS storage as all launchers are terminated. These cost details will be posted shortly. Archived projects will have a much smaller storage rate and will likely not be charged to individual research budgets.   

