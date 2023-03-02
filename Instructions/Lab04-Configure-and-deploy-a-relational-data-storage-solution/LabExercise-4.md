# Instructions

## Exercise 4: Enable Geo Replication & Test Failover.

In this Exercise you are going to configure active geo-replication for Azure SQL Database using the Azure portal and to initiate failover.

In this Exercise, you will:

  + Task 1: Configure Replica of Primary database
  + Task 2: Initiate a failover

### Estimated Timing: 50 minutes

### Task 1: Configure Replica of Primary database

In this task you are going to configure a replica of your primary database.

#### Steps:

1. In the Azure portal, browse to the database that you have created on the previous exercise to set up for geo-replication.

2. On the SQL Database page, select your database, scroll to Data management section, select **Replicas**, and then select **+ Create replica**.

    ![img](../media/rep1.png)
    
3. Create the secondary database server. You can choose any region for your secondary server, but the paired region is recommended. Please click on **Create new** for Server.

    ![img](../media/rep2.png)
    
4. For creating new server, please enter the following details and then click on **Ok**:

    | Settings | Values |
    |  -- | -- |      
    | Server name | **contososervwest** |
    | Location | **West US** (It is the paired region of East US) |
    | Authentication method | **Use SQL authentication** |
    | Server admin login | **contosoadmin** 
    | Password |  **Contoso@123** 
    | Confirm password | **Contoso@123** |    

    ![img](../media/rep3.png)

5. After providing the server details, under **Compute + Storage** option, check whether it has the same database configuration of the primary database which is **General Purpose (Standard-series (Gen5), 2 vCores, 32 GB storage)**, if not please change the configuration by clicking on configure database and select the configuration of primary database. Please keep other options default values as it is.

6. Please Select **Review + Create**, then click **Create**.

    ![img](../media/rep4.png)
    
7. You can see a notification of **Deployment in Progress**, please wait for a while, then you can see **Your deployment is complete** notification.

8. Please click on **Go to resource**.

    ![img](../media/rep5.png)

9. You can see the replica of **adventureworkscontoso** database with new server named **contososervwest**.

    ![img](../media/rep6.png)

10. Return to the **primary database** page, and then select **Replicas**. Your secondary database is listed under **Geo replicas**.

    ![img](../media/rep7.png)

  Next you are going to initiate a failover thereby your secondary database becomes your primary database.    

### Task 2: Initiate a failover

In this task you are going to initiate a failover thereby your secondary database becomes your primary database.

#### Steps:

1. Go to the Primary database in the azure portal.

2. Scroll to Data management section, and then select Replicas.

3. In the Geo replicas list, select the secondary database you want to enable as primary, select the ellipsis **(...)** on the right side of the secondary database, and then select **Forced failover**.

    ![img](../media/rep8.png)
 
 4. A dialogue box will appear asking for Forced failover will switch adventureworkscontoso database to the primary role. Please select **Yes** on the dialogue box.

    ![img](../media/rep9.png)

5. You will get a notification saying **Request submitted for failover replication**.

6. Now under the database named **adventureworkscontoso (contososervwest/adventureworkscontoso)** select **Replicas**, then you can see under **Primary** the name of the current database with server **contososervwest** having a **pending** status.

  ![img](../media/rep10.png)

7. Please keep refreshing the page and you will see that the primary database status will become **Online**.

![img](../media/rep11.png)


### Review

In this lab, you have:

+ Configured a replica of your primary database via azure portal.
+ Initiated a failover thereby you have seen the secondary database became primary.
