# Instructions

## Exercise 2: Deploy Azure Container instance using a YAML file

In this exercise, you are going to deploy an Azure Container instance by using YAML file and review the functionalities of it.

In this Exercise, you will have:

  + Task 1: Deploy an Azure container instance by using YAML file.

### Estimated Timing: 45 minutes

### Task 1: Deploy an Azure container instance by using YAML file.

In this task, you are going to deploy an Azure container instance by using YAML file.

#### Steps:

1. Go to Azure portal, from the top please select **Cloud shell**. Then select **Bash**

![img](../media/yml3.png)

2. Please select **Show advanced settings**.

![img](../media/yml4a.png)

3. On the **Create a Storage account** page please enter the following details and select **Create storage**.
    
    | Setting | Action |
    | -- | -- |
    | **Subscription** drop-down list | Retain the default value |
    | **Resource group** section | PLease click on **Use existing** then Select **ODL-AZ-305M05C - XXXXX** |
    | **Storage account** [Create new] | Enter **contosostor** |
    | **Region** drop-down list | Select **(US) East US** |
    | **File share** [Create new] | Enter **contosofile1** |
    
    *The following screenshot displays the configured settings in the **Create a storage account** blade.*

![img](../media/yml5.png)
 
4. Please wait for sometime and let the **Bash** terminal open.

5. Please enter the command ***code deploy-aci.yaml*** to create an empty YAML file to write the scripts.

6. You can see an empty YAML file created in the name of **deploy-aci.yaml**.

![img](../media/yml6.png)

7. Please copy the following YAML script to the **deploy-aci.yaml** file.

```YAML
apiVersion: 2019-12-01
location: eastus
name: securetest
properties:
 containers:
 - name: mycontainer
   properties:
     environmentVariables:
      - name: 'ACCEPT_EULA'
        value: 'Y'
      - name: 'MSSQL_SA_PASSWORD'
        value: 'India@123'
     image: mcr.microsoft.com/mssql/server:2019-CU12-ubuntu-20.04
     ports:
     - port: 1433
     resources:
       requests:
        cpu: 2
        memoryInGB: 2
 osType: Linux
 restartPolicy: Always
tags: null
type: Microsoft.ContainerInstance/containerGroups
```
Let’s understand the script before executing it in the terminal for container deployment.

  + **location**: It is the Azure region where we want to deploy the resources
  + **Container properties**:
      +  Define environment variables using keys “name” and "value".
  + **Image**: The azure container image for SQL Server.
  + **Ports**: Enter the SQL Server port number for communications. We will be using the default port 1433 in this section.
  + Specify **cpu** and **memoryInGB** in the script for the container configuration.
  + **OS type**: Linux. *It should be as per the application image we specified in the script.*
  + **Type**: It is the Azure container type. Its value will be – *Microsoft.CotainerInstance/containerGroups*

Your YAML file should look like this:

![img](../media/yml7.png)

8. Right click in the editor and click on **Save** to write the file and then **Quit** to exit from the editor.

8. Now enter the command ***az container create --resource-group ODL-AZ-305M05C-<inject key="DeploymentID" enableCopy="false"/> --file deploy-aci.yaml***

9. You get JSON script output that shows the Azure Container instance is deployed successfully.

![img](../media/yml8.png)

10. Go to **Resource groups**, then select **ODL-AZ-305M05C-XXXXX**, on the **Overview** section you can see the container instance named **securetest**. please select the container instance.

![img](../media/yml9.png)

11. On the overview section, you can see the status as **Running**.

![img](../media/yml10.png)


#### Review

In this lab, you have:

- Deployed an Azure Container instance using YAML file.
