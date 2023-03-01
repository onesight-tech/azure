****
### Log analytics data ingestion
----------
The ingestion quota of data to log-analytics will increase exponentially when used with AKS or any other computation services. So, for non-production it’s always better to limit the data to some "x" amount of GB to restrict the cost.
****
### Setting LRS in storage account
----------
The redundancy option in storage account if set it as Global, each and every data insert will be written in the paired region of storage account. This will make the operation costlier with data size and also with badnwidth consumption because of transfer. So it's always better to set it as locally redundant for non-production storage accounts.
****
### VM and VMSS size restriction
----------
The size of VMs based on the requirement of each project can be restricted. This policy will help in not allocating more number of CPUs and Memory to the VM. In turn this will reduce the consumption cost.
****
### PostgreSQL SKU restriction
----------
The database SKU restriction is a best approach for non production resources. We are giving PostgreSQL sample, the same can be applied for various DB types.
****
### SQL policies
----------
The SQL DB / ManagedInstances usually incurs cost because of the SKUs being chosen or the capacity mentioned. The policies should limit or report this choice.

For MI - having vCores less than 24 should be more than enough in non-prod. It's always good to start with 8 vCores in non-prod, and can be increased as the demand increases.
****
### Application Gateway
----------
For non-production or lower environments, it's better not to have WAF (Web Application Firewall) enabled. This will reduce the cost of application gateway in half.