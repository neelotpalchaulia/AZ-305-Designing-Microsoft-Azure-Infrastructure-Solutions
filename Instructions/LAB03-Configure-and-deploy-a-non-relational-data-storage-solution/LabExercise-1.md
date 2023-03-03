## Instructions

## Exercise 1: Create Storage account, configure a static website and apply lifecycle management policy

In this exercise you are going to create a storage account and configure a static website to access the blob container and apply lifecycle management policy.

In this Exercise, you will have:

+ Task 1: Create an Azure Storage account.
+ Task 2: Create a blob container.
+ Task 3: Upload a block blob.
+ Task 4: Configure a static website to access the blob container.
+ Task 5: Apply the lifecycle Management Policy.

## Estimated timing: 60 minutes

### Task 1: Create an Azure Storage account

In this task, you will learn how to use Azure portal to create an Azure storage account.

#### Steps

1. Double click on the Edge browser icon from the desktop.

2. Enter the **login credentials**. For credentials, please see the environment details tab on the lab guide.

3. Once the portal opens completely, click on **All services** on the left portal menu and select storage accounts

    ![image](../media/str1.png)

4. On the storage accounts page, please select **Create**. 

    ![image](../media/str2.png)

5. Create a Storage account page will open. You can see the options for your new storage account are organized into tabs in the Create a storage account page.

6. Basic tab shows a standard configuration of the basic properties for a new storage account. On the **Basics tab**, select the subscription, if the default subscription is being used, then select the **resource group**.

7. For Storage account name option, please provide **azstrg<inject key="Deployment-id" />** name in small case and numbers.

8. Select the **Region** option as **East US**

9. On the **Performance** options: Select **Standard**

10. Select Geo-Redundant storage on the redundancy option

    ![image](../media/str4a.png)

11. Go to Advanced tab, review the options and the default values of it. Please don't change any values.

12. Go to Networking tab, and review the options and the default values.

13. Go to Data Protection tab, and review the options and the default values.

14. Go to Encryption tab, and review the options and the values.

15. After reviewing all tabs, select the review button from the bottom left of the page.

    ![image](../media/str5.png)

16. After completing the validation, please click on Create button from the bottom left of the page.

    ![image](../media/str6.png)

17. After completing the deployment, Please click on **Go to resource**.

    ![image](../media/str7.png)

18. You can see the newly created Storage account, please go through the overview section.

    ![image](../media/str8.png)

### Task 2: Create a blob container

In this task, you will learn how to use the Azure portal to create a blob container in a storage account.

#### Steps

1. Navigate to your new storage account in the Azure portal.

2. In the left menu for the storage account, scroll to the **Data storage** section, then select **Containers**.

3. Select the + Container button.

    ![image](../media/str9.png)

4. Enter `azblobcs` as the name for your new container. The container name must be lowercase, must start with a letter or number, and can include only letters, numbers, and the dash (-) character. For more information about container and blob names, see Naming and referencing containers, blobs, and metadata.
    - Container Name: `azblobcs`

5. Set the level of public access to the container. The default level is Private (no anonymous access).

6. Select **Create** to create the container.

    ![image](../media/str10.png)

7. After completing the deployment, you can see the newly created blob container on the container's section. If its not listed please refresh the page.

    ![image](../media/str11.png)

### Task 3: Upload a block blob

In this task, you will learn how to use the Azure portal to upload a block blob in your newly created blob container in a storage account. To upload a block blob to your new container in the Azure portal, follow these steps:

#### Steps

1. In the Azure portal, navigate to the container you created in the previous task.

2. Select the container to show a list of blobs it contains. This container is new, so it won't yet contain any blobs.

    ![image](../media/str11.png)

3. Select the **Upload** button to open the upload blade and browse your local file system to find a file to upload as a block blob ( you can upload multiple files). You can optionally expand the Advanced section to configure other settings for the upload operation. Please upload some image files, if it's not available in the pictures folder, you can download from internet and use that files to upload to the block blob.

    ![image](../media/str12a.png)

4. After entering all the details, please select the **Upload** button to upload the blob.

    ![image](../media/str13.png)

5. After completing the uploading process of block blobs, you can see the blobs listed in the container. If its not seeing, Please select the overview tab of the container and select refresh.

    ![image](../media/str14.png)

### Task 4: Configure a static website to access the blob container

In this task, you will learn how to use the Azure portal to configure a static website to access the blob container. To configure a static website to access the blob container, follow these steps:

#### Steps

1. Launch **Visual Studio Code** by double click on Vscode icon from desktop.

2. On the toolbar, click **Extensions**. Search for **Azure Storage**, and select the **Azure Storage extension** from the list. Then click the **Install** button to install the extension.

    ![image](../media/str15.png)

3. Open the Azure portal in your web browser.

4. Locate your storage account and display the account overview.

    ![image](../media/str8.png)

5. Select **Static website** to display the configuration page for static websites under **Data Management** section.

6. Select Enabled to enable static website hosting for the storage account.

7. In the **Index document name** field, specify a default index page of **index.html**. The default index page is displayed when a user navigates to the root of your static website.

8. In the **Error document path** field, specify a default error page of **404.html**. The default error page is displayed when a user attempts to navigate to a page that does not exist in your static website. Click **Save**.

    ![image](../media/str16.png)

9. The Azure portal now displays your static website endpoints (primary and secondary). Azure Storage automatically creates a container named **$web**. The $web container will contain the files for your static website.

    ![image](../media/str17.png)

Next, create a Hello World web page with Visual Studio Code and deploy it to the static website hosted in your Azure Storage account.

10. Create an empty folder named **mywebsite** on your local file system.

11. Launch Visual Studio Code, and open the folder that you just created from the **Explorer** panel, by selecting open folder option.

    ![image](../media/str18.png)

12. Select **Yes, I trust the authors** Trust folder and enable all features.

    ![image](../media/str19.png)

13. Create the default index file in the mywebsite folder, by selecting Add file option and provide the name **index.html** in the name box.

    ![image](../media/str20.png)

14. Open index.html in the editor, paste the following html script into the file, and save it:

    ```<!DOCTYPE html>
    <html>
    <body>
      <h1>Hello World!</h1>
    </body>
    </html>
    ```

   ![image](../media/str21.png)

15. Create the default error file and name it **404.html**.

16. Open 404.html in the editor, paste the following text into the file, and save it:

    ```<!DOCTYPE html>
        <html>
        <body>
        <h1>404</h1>
        </body>
        </html>
    ```


    ![image](../media/str22.png)

17. Click on the **Azure** logo where you will be asked to log in. Once you have authenticated to Azure with the extension, expand the **Subscription** then **Storage accounts**, under it expand the storage account you have created, then expand **Blob containers**, then right-click on the **$web** storage container. You’ll see an option to **Deploy to Static Website via Azure storage**. Select that option.

    ![image](../media/str23.png)

18. Choose the folder containing the two files mentioned earlier. 

    ![image](../media/str24.png)

19. Visual Studio Code will then deploy those files as your static page and return a success message to you. Please select  **Browse to website button** once the files have been uploaded, navigate to the primary endpoint you received earlier.

    ![image](../media/str25.png)

20. This is the index.html page you uploaded through Visual studio code. Now you can see it in as Azure hosted static website.

    ![image](../media/str26.png)

### Task 5: Apply the lifecycle Management Policy

In this task, you will learn how to use the Azure portal to Apply the lifecycle management policy of a storage account. Azure Storage lifecycle management offers a rule-based policy that you can use to transition blob data to the appropriate access tiers or to expired data at the end of the data lifecycle. A lifecycle policy acts on a base blob, and optionally on the blob's versions or snapshots. For example, if you have defined an action to move a blob from the hot tier to the cool tier if it has not been modified for 30 days, then the lifecycle management policy will move the blob 30 days after the last write operation to that blob.

#### Pre-requisites for this task

Before doing the steps to configure Lifecycle management policy, please go to the storage account created on the previous task and select **Configuration** under **Settings** to view the configuration of your storage account, which you are going to apply Lifecycle management policy.

   ![image](../media/life1.png)

#### Steps

1. Go to **Lifecycle management** under **Data management** of the storage account created on the previous task. Please select **Add rule**.

    ![image](../media/life2.png)

2. On the **Add a rule** page please enter the **Rule name** as **Testrule** and keep the default settings as it is and select **Next**

    ![image](../media/life3a.png)

3. On the Add a rule page, under the **Base blob** tab, enter the following settings as per the image below: and please select **Add** button.

    ![image](../media/life4.png)

4. You have now created your lifecycle management policy for storage blobs, after 30 days, your storage blobs will be moved to the cool access tier.

    ![image](../media/life5.png)

If you are not seeing newly created lifecycle management policy please select the lifecycle management and select refresh.
    
#### Review

In this lab, you have:

- Created a Storage account
- Configured a static website to access the blob container
- Applied Lifecycle Management policy
