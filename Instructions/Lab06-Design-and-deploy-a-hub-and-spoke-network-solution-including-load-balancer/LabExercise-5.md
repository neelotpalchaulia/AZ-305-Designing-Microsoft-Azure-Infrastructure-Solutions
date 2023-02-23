# Instructions

## Exercise 5: Create security configuration and Deploy the security admin configuration

A security admin configuration contains a set of rule collections. Each rule collection contains one or more security admin rules. You then associate the rule collection with the network groups that you want to apply the security admin rules to. In this exercise you will create security configuration and deploy security admin coniguration.

In this Exercise, you will have:

  + Task 1: Create security configuration.
  + Task 2: Deploy the security admin configuration.

### Estimated Timing: 30 minutes

### Task 1: Create security configuration

In this task, you are going to create secuirty configuration for the virtual network manager created on the previous exercise.

#### Steps:

1. Go to the **contosonetmanager** page, select **Configuration** under **Settings**, then select **+ Create**. Select **Security Configuration** from the menu to begin configuration of SecurityAdmin.

    ![img](../media/secu1.png)

2. Enter the name **contososec** for the configuration, then select **Next: Rule collections**.

    ![img](../media/secu2.png)

3. Under **Rule Coolections** tab, select **+ Add**.

    ![img](../media/secu3.png)

4. On the **Add a rule collection** page, enter the name as **contososecuritycol** then select **contosonetworkgrp** as **Target network group**. Click **+ Add**.

    ![img](../media/secu5.png)

5. On the **Add a rule** side screen, enter the following details:

    | Section | Values |
    | ------- | ------ |
    | Name | **DenyInternet** |
    | Description | **This rule blocks traffic to the internet on HTTP and HTTPS** |
    | Priority | **1** |
    | Action | Select **Deny** |
    | Direction | Select **Outbound** |
    | Protocol | Select **TCP** |
    | Destination port | Enter **80, 443** |

    ![img](../media/secu6.png)

6. After adding the security admin rule, select **Add**.

    ![img](../media/secu7.png)

7. Select **Review + Create** and then **Create**.

8. On the Configuration section, you can see the security configuration named **contososec**.

    ![img](../media/secu8.png)

### Task 2: Deploy the security admin configuration

In this task, you are going to deploy the security admin configuration.

#### Steps:

1. Select **Deployments** under **Settings**, then select **Deploy configurations**.

2. Under Configurations, Select **Include security admin in your goal state** and the **contosoSec** configuration you created in the previous task. Then select West US and East US as the target regions and select **Next**.

    ![img](../media/secu9.png)

3. Select **Deploy**.

   >**Note:** You should now see the deployment show up in the list for the selected region. The deployment of the configuration can take several minutes to complete.

    ![img](../media/secu10.png)

### Review

In this lab, you have:

+ Created security configuration.
+ Deployed the security admin configuration.
