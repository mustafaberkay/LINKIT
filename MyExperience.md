#My experience and further notes

Firstly, I have to say that I did not have any experience in cloud computing before. When I saw the assignment, I was surprised a bit. However, I made lots of research on it and tried to do my best. Trying to work on a topic that I did not experience is a great challenge for me to overcome ant it is a great chance of improving myself. Also, I understood the importance of cloud computing in data engineering when I was reading Blob Storages which contains unstructured data. Thank you for giving me this chance.

## Azure Storage Account

Quesitons to be asked:
<br>1) Which kind of Storage Account do you want? (General Purpose v1, General Purpose v2 or Blob Storage)
<br>2) Do you want to use your own access keys?
<br>3) Do you want your data tobe accessed only from your network or through Virtual Networks?
<br>4) Do you want to replicate your Storage Account?
<br> From the configuration menu under the settings portal I can configure the Deployment model, Performance, Account kind, Replication etc. For securing an Azure Storage Account, there are several ways to do depending on your need:
<br>-with Microsoft Azure I can automatically encrypt all of your data written to Azure Storage by using Storage Service Encryption (SSE).
<br>-I would assign Role-Based Access Control (RBAC) roles scoped to the storage account to security principals and use Azure AD to authorize resource management operations such as key management.
<br>-Data in transit means that your data is transferred from one point to other. If you transmit your data without securing, it attracts the hackers who want to access your data. So I would use some technics, for example, data can be secured in transit between an application and Azure by using Client-Side Encryption, HTTPS, or SMB 3.0.
<br>-Also even your data is at rest it does not mean that you are secure. So, I would also encrypt the data at rest as well.

<br>Another feature that Microsoft Azure provides us is that you can monitor the Logs in Storage Account. This includes data reading and writing as well. So step by step:
<br>-In the Azure portal, select Storage accounts, then the name of the storage account to open the storage account blade.
<br>-Select Diagnostics in the MONITORING section of the menu blade.
<br>-Ensure Status is set to On, and select the services for which you'd like to enable logging. (In our case It is Writing)
<br>-Click Save.
## VNet-to-VNet
In general there are two reasons to create VNet-to-VNet and these are:
<br> Cross region geo-redundancy and geo-presence
<br>-You can set up your own geo-replication or synchronization with secure connectivity without going over Internet-facing endpoints.
<br>-With Azure Traffic Manager and Load Balancer, you can set up highly available workload with geo-redundancy across multiple Azure regions. One important example is to set up SQL Always On with Availability Groups spreading across multiple Azure regions.
<br> Regional multi-tier applications with isolation or administrative boundary
<br>-Within the same region, you can set up multi-tier applications with multiple virtual networks connected together due to isolation or administrative requirements.
<br>So I would ask if any of those reasons are valid for the case.
<br>The easiest way of doing VNet Peering also can be done by Microsoft Azure Portal. 
<br>1)Create virtual networks. For example, MyVnet1 and MyVnet2
<br>2)In the Search box at the top of the Azure portal, begin typing MyVnet1. When MyVnet1 appears in the search results, choose it.
<br>3)Select Peerings, under Swttings, and then press [+ Add] button.
<br>4)In the Add Peering Screen, Enter the Name	"MyVnet1-MyVnet2".
<br>5)In the Search box at the top of the Azure portal again, begin typing MyVnet2. When MyVnet2 appears in the search results, choose it.
<br>6)Now do the same process for MyVnet2.

### Application Gateway

Azure Application Gateway gives you application-level routing and load balancing services that let you build a scalable and highly-available web front end in Azure. You control the size of the gateway and scale your deployment based on your needs.
<br>If you want to protect your application from common web vulnerabilities and exploits like SQL Injection or Cross site scripting or customize rules to reduce false positives.
<br>With the Application Gateway you can be even more specific. For example, you can route traffic based on the incoming URL. So if /images is in the incoming URL, you can route traffic to a specific set of servers (known as a pool) configured for images. If /video is in the URL, that traffic is routed to another pool optimized for videos.


