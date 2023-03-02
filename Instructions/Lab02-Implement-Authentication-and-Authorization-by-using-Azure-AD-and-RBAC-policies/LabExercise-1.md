# Instructions

## Exercise 1: Add a user and provide the accessibility of the resources.

In order to allow Contoso users to authenticate by using Azure AD, you have been tasked with provisioning users and group accounts. 

In this exercise, you will:

+ Task 1: Create and configure Azure AD users 
+ Task 2: Add Accessibility of Resources

### Estimated Timing : 30 minutes

### Task 1: Create and configure Azure Active Directory users

In this task you are going to create and configure Azure Active Directory users.

#### Steps:

1. Sign in to the [Azure portal](https://portal.azure.com).

2. In the Azure portal, Go to **All Services** and select **Azure Active Directory**.

    ![img](../media/use1.png)

3. On the Azure Active Directory blade, scroll down to the **Manage** section, click **User settings**, and review available configuration options.

    ![img](../media/nuse1.png)

4. On the Azure Active Directory blade, in the **Manage** section, click **Users**, and then click your user account to display its **Profile** settings. 

    ![img](../media/nuse2.png)

5. Click **Edit properties**, in the **Settings** section, and check the usage location is United States, if not set **Usage location** to **United States** and click **Save** to apply the change.

    ![img](../media/nuse3.png)

    >**Note**: This is necessary to assign an Azure AD Premium P2 license to your user account later in this lab.

6. Go back to the **Users - All users** blade, and then click **+ New user**.

    ![img](../media/nuse4.png)

7. In the new user page please enter the following settings (leave others with their defaults) and select **Save**.

    | Setting | Value |
    | --- | --- |
    | Username | **az305-01a-aaduser1** |
    | Name | **az305-01a-aaduser1** |
    | Let me create the password | enabled |
    | Initial password | **Provide a secure password** |
    | Usage location | **United States** |
    | Job title | **Cloud Administrator** |
    | Department | **IT** |

    >**Note**: **Copy to clipboard** the full **User Principal Name** (user name plus domain). You will need it later in this task.

7. Refresh the users page you can see the newly created user named **az305-01a-aaduser1**.


### Task 2: Add Accessibility of Resources

In this task you are going to give resource accessibility to the user az305-01a-aaduser1.

#### Steps:

1. Go to Azure portal, search **Resource groups** on the search box of the Home page and select **Resource groups** from the list.

2. Select the resource group named **ODL-AZ-305M02B-XXXXXXX**.

    ![img](../media/nres1.png)

3. In the resource group page, please select **Access control (IAM)**, then select **+Add**, then select **Add role assignment**.

    ![img](../media/nres2.png)

4. In the **Add role assignment** page, please select **Virtual machine contributor** role by searching on the search bar and then select **Next** at the bottom.

    ![img](../media/nres3.png)

5. In the **Members** tab, please select **+Select members**, then select the user **az305-01a-aaduser1**, and select **Select**.

    ![img](../media/nres4.png)

6. Please select **Review + Assign** at the bottom, review the role assignment settings.

    ![img](../media/nres5.png)

7. Click **Review + assign** to assign the role.

   After a few moments, the user is assigned the Virtual Machine Contributor role at the **ODL-AZ-305-M02B-XXXXXXX** resource group scope.

    ![img](../media/nres6.png)

#### Review

In this lab, you have:

- Created and configured Azure AD users.
- Provide accessibility to the resources.
