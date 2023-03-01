# Instructions

## Exercise 3: Create a dynamic network group

In this exercise you will set up a dynamic network group.

In this Exercise, you will:

  + Task 1: Create a dynamic group.

### Estimated Timing: 30 minutes

### Task 1: Create a dynamic group.

#### Pre-requisites for this task

Complete Exercise 1 & Exercise 2.

#### Steps:

1. Go to your Azure Virtual Network Manager instance named **contosonetmanager**.

2. On the **contosonetmanager** page, under **Setting** select **Network groups**, then select **+ Create**.

    ![img](../media/dyn1.png)

3. On the **Create network group** side screen, enter the name as **contosonetworkgrp**.

4. On the description, enter **This network group contain virtual networks in the East US region**, then click **Create**.

    ![img](../media/dyn2.png)

5. From the Network groups page, select the created network group to configure the network group.

    ![img](../media/dyn3.png)

6. On the Overview section of the **contosonetmanager/contosonetworkgrp** page, select **Create Azure Policy** under **Create policy to dynamically add members**.

    ![img](../media/dyn4.png)

7. On the **Create Azure Policy** page, select the following information, then click **Save**.

    | Section | Values |
    | ------- | ------ |
    | Policy name | Enter **VNetPolicy-a** in the text box. |
    | Scope | Scope already selected, if its not, please select the current subscription. |
    | Parameter | Select **Name** from the drop-down.|
    | Operator | Select **Contains** from the drop-down. |
    | Condition | Enter **EastUS** to dynamically add the two East US virtual networks into this network group. |
  
    ![img](../media/dyn5.png)

8. Under **Settings**, select **Group Members** to view the membership of the group based on the conditions defined in Azure Policy. If it's not visible then click on **Refresh**.

    ![img](../media/dyn6.png)

### Review

In this lab, you have:

+ Deployed dynamic network group.
+ Added an azure policy to dynamically add the networks into the group.
