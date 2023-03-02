# Instructions

## Exercise 1: Create Azure resources

In this exercise, you are going to create an Azure storage account and a function app. Azure Functions are best suited for small apps with events that can function independently of other websites.

In this exercise, you will have:

  + Task 1: Create an Azure Storage account.
  + Task 2: Create a function app

### Estimated Timing: 30 minutes

### Task 1: Create an Azure Storage account

In this task, you will create an Azure storage account.

#### Steps:

1. In the Azure portal, use the search bar to search for **Storage Accounts**, and then, in the list of results, select **Storage Accounts**.

1. On the **Storage accounts** blade, select **+ Create**.

    ![img](../media/servl1.png)

1. On the **Create a storage account** blade, on the **Basics** tab, perform the following actions, and then select **Review**:

    | Setting | Action |
    | -- | -- |
    | **Subscription** drop-down list | Retain the default value |
    | **Resource group** section | Select **Serverless - XXXXX** |
    | **Storage account name** text box | Enter **contosofuncstor** |
    | **Region** drop-down list | Select **(US) East US** |
    | **Performance** section | Select the **Standard** option |
    | **Redundancy** drop-down list | Select **Locally-redundant storage (LRS)** |

    The following screenshot displays the configured settings in the **Create a storage account** blade.

    ![img](../media/servl2.png)   

1. On the **Review** tab, review the options that you selected during the previous steps.

1. Select **Create** to create the storage account by using your specified configuration.

    > **Note**: Wait for the deployment to complete before you proceed with this lab.

1. On the **Overview** blade, select the **Go to resource** button to go to the blade of the newly created storage account.

1. On the **Storage account** blade, in the **Security + networking** section, select **Access keys**.

1. On the **Access keys** blade, select **Show keys**.

    ![img](../media/servl3.png) 

1. Review any one of the keys, and then copy the value of either of the **Connection string** to the clipboard

     > **Note**: It doesn't matter which connection string you choose. They are interchangeable.

1. Open Notepad, and then paste the copied connection string value to Notepad. You'll use this value later in this lab.


### Task 2: Create a function app

In this task, you will create a function app.

#### Steps:

1. In the Azure portal, enter **function app** in the search bar, then select **Function App** from the list.

    ![img](../media/servl4.png) 

1. On the **Function App** blade, select **Create**.

    ![img](../media/servl5.png) 

1. On the **Create Function App** blade, on the **Basics** tab, perform the following actions, and then select **Next: Hosting**:

    | Setting | Action |
    | -- | -- |
    | **Subscription** drop-down list | Retain the default value |
    | **Resource group** section | Select **Serverless-XXXXXX** |
    | **Function App name** text box | Enter **contosofunclogic** |
    | **Publish** section | Select **Code** |
    | **Runtime stack** drop-down list | Select **.NET** |
    | **Version** drop-down list | Select **6** |
    | **Region** drop-down list | Select the **East US** region |
    | **Operating System** option | Select **Linux** |
    | **Plan type** drop-down list | Select **Consumption (Serverless)** |

    The following screenshot displays the configured settings in the **Create Function App** blade.

    ![img](../media/servl6.png)    

1. On the **Hosting** tab, perform the following actions, and then select **Review + create**:

    | Setting | Action |
    | -- | -- |
    | **Storage account** drop-down list | Select the **contosofuncstor** storage account |
    
    ![img](../media/servl7.png)      

1. On the **Review + create** tab, review the options that you selected during the previous steps.

1. Select **Create** to create the function app by using your specified configuration.

    > **Note**: Wait for the deployment to complete before you move forward with this lab.

#### Review

In this lab, you have:

- Created a storage account.
- Created a function app.


