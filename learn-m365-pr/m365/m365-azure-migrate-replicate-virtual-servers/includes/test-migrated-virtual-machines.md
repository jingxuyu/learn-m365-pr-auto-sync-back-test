Once your targeted virtual machines are replicated and into Azure, before you migrate them into production, you can test them to ensure everything works. 
1.	Start by clicking Replicating Servers in the Azure Migrate: Server Migration tile. 

    ![Screenshot 1](../media/screenshot-1.png)

2.	In the list of servers, find the one you want to test and select Test Migration from the ellipses for the group just migrated. 

    ![Screenshot 2](../media/screenshot-2.png)

3.	In Test Migration, select the Azure Virtual Network to use for the test. We recommend you use a non-production VNET.

    ![Screenshot 3](../media/screenshot-3.png)
 
The process runs a prerequisite check, prepares for the test, creates a new test virtual machine, and starts it. This takes a few minutes.
