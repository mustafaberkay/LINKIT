#My experience and further notes

Put here general information about the steps you took, what you liked, disliked, why did you do X instead of Y and so on.

## Azure Storage Account

Quesitons to be asked
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

I did X because of Y...
<br>I had issues with Z...
<br>I liked doing T...

### Application Gateway

I did A because of B...
<br>I had issues with C...
<br>I liked doing D...

