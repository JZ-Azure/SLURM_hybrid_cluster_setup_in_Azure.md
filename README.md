This post is to demonstrate how to setup SLURM federation between an on-prem cluster and an Azure cluster. Both clusters will be deployed by [azhop](https://azure.github.io/az-hop/). Please refer to the azhop documentation on how to deploy an HPC environment on Azure. 

## About SLURM federation
Slurm Federation is a feature of the Slurm Workload Manager, a highly scalable and flexible open-source cluster management and job scheduling system commonly used in high-performance computing (HPC) environments.

A Slurm Federation allows multiple independent clusters to be connected and managed as a single entity. This enables users to submit jobs to the federation as a whole, rather than to a specific cluster. The jobs are then automatically routed to the appropriate cluster for execution, based on the available resources and the job requirements. This can help to improve the utilization of resources across multiple clusters, increase the efficiency of job scheduling, and provide a more seamless user experience.

In a Slurm Federation, each participating cluster is considered a member of the federation and operates as a separate entity. The members communicate with each other using the Slurm messaging layer, and a centralized management entity is responsible for coordinating the scheduling and execution of jobs across the federation.

Slurm Federation is a relatively new feature, and its implementation and use can be complex. However, it has the potential to greatly enhance the capabilities of HPC systems and support the efficient use of resources in large-scale computing environments.

## Add scheduler node network security group (NSG) rules and setup virtual network peering
To setup SLURM federation we need to enable slurmdbd communications between on-prem and cloud clusters. New NSG rules and vnet peering need to be added to enable the commnucation. 
