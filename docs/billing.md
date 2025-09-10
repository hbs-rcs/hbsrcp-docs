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

Active projects incur project storage and launcher costs. The cost of running launcher sessions will vary based on the configuration selected; see the below table for hourly rates of the different launcher configurations. A stopped launcher will incur minor costs (due to storage). There is no cost for unlaunched launchers. You can associate as many launchers with a project as you’d like and will only incur costs when a session is created. 

| Launcher Type | Configuration Name               | Cores   | Memory | GPU? | Hourly Cost |
| ------------- | ------------------               | -----   | ------ | ---- | ----------- |
| JupyterLab    |	Medium-general-purpose-instance	 | 2 cores | 4 GB   |	     | $0.04 |
| JupyterLab	  | Large-general-purpose-instance	 | 2 cores | 8 GB   |      | $0.09 |
| JupyterLab	  | Large-compute-optimized-instance | 2 cores | 4 GB   |		   | $0.10 |
| Rstudio	      | Large-general-purpose-instance	 | 2 cores | 8 GB   |      | $0.09 |
| Rstudio	      | Large-compute-optimized-instance | 2 cores | 4 GB   |      |	$0.10 |
| Rstudio | Large-general-purpose-instance | 2 cores | 8 GB |  | $0.09 |
| Rstudio | Medium-compute-optimized-instance | 1 core | 2 GB |  |  |
| Rstudio | Large-compute-optimized-instance | 2 cores | 4 GB |  | $0.10 |
| Rstudio | Accelerated-instance-for-ML | 4 cores | 16 GB | GPU | $0.53 |
| Rstudio | Extra-large-general-purpose-instance | 4 cores | 16 GB |  | $0.17 |
| Rstudio | Compute-memory-balanced-large-instance | 4 cores | 16 GB |  | $0.19 |
| Rstudio | Memory-optimized-large-instance | 2 cores | 16 GB |  | $0.13 |
| Rstudio | Memory-optimized-extra-large-instance | 4 cores | 32 GB |  | $0.25 |
| Rstudio | Memory-optimized-double-extra-large-instance | 8 cores | 64 GB |  | $0.50 |
| Spyder | Large-general-purpose-instance | 4 cores | 16 GB |  | $0.17 |
| Spyder | Extra-large-general-purpose-instance | 8 cores | 32 GB |  | $0.33 |
| Spyder | Large-compute-optimized-instance | 8 cores | 16 GB |  | $0.41 |
| Spyder | Extra-large-compute-optimized-instance | 16 cores | 32 GB |  | $0.82 |
| Spyder | Extra-large-accelerated-instance | 4 cores | 16 GB | GPU |  |
| Stata | Medium-general-purpose-instance | 2 cores | 4 GB |  | $0.04 |
| Stata | Large-general-purpose-Instance | 2 cores | 8 GB |  |  |
| Stata | Large-general-purpose-instance | 4 cores | 16 GB |  | $0.17 |
| Stata | Extra-double-large-general-purpose-instance | 8 cores | 32 GB |  | $0.33 |
| Stata | Large-compute-optimized-instance | 8 cores | 16 GB |  | $0.41 |
| Stata | Extra-large-compute-optimized-instance | 16 cores | 32 GB |  | $0.82 |
| Stata | Extra-large-general-purpose-instance | 4 cores | 16 GB | GPU | $1.01 |
| VSCode | Medium-general-purpose-instance | 2 cores | 4 GB |  |  |
| VSCode | Large-general-purpose-instance | 2 cores | 8 GB |  | $0.09 |
| VSCode | Medium-compute-optimized-instance | 1 core | 2 GB |  |  |
| VSCode | Large-compute-optimized-instance | 2 cores | 4 GB |  | $0.10 |
| VSCode | Accelerated-instance-for-ML | 4 cores | 16 GB | GPU | $0.53 |
| VSCode | Accelerated-g4extralarge-instance-for-ML | 48 cores | 192 GB | GPU | $3.91 |
| VSCode | Accelerated-g6extralarge-instance-for-ML | 48 cores | 192 GB | GPU | $4.60 |
| VSCode | Extra-large-general-purpose-instance | 4 cores | 16 GB |  | $0.17 |
| VSCode | Compute-memory-balanced-large-instance | 4 cores | 16 GB |  | $0.19 |
| VSCode | Memory-optimized-large-instance | 2 cores | 16 GB |  | $0.13 |
| VSCode | Memory-optimized-extra-large-instance | 4 cores | 32 GB |  | $0.25 |
| VSCode | Memory-optimized-double-extra-large-instance | 8 cores | 64 GB |  | $0.50 |
| sagemakerCanvas | SageMaker-Canvas-Default |  |  |  |  |
| sagemakerNotebook | Medium-instance-SageMaker | 2 cores | 4 GB |  |  |
| sagemakerNotebook | Large-instance-SageMaker | 2 cores | 8 GB |  | $0.08 |
| sagemakerNotebook | Extra-large-instance-SageMaker | 4 cores | 32 GB |  | $0.17 |
| sagemakerNotebook | ml.g4dn.xlarge | 1 core | 4 GB | GPU | $0.74 |

TEST:

{{ read_csv('RCP_Rate_Sheet.csv') }}

### Dormant and Archived Projects 

Dormant and archived project costs will be for storage only. Dormant project storage rates are similar to active ones, but with no EFS storage as all launchers are terminated. These cost details will be posted shortly. Archived projects will have a much smaller storage rate and will likely not be charged to individual research budgets.   

