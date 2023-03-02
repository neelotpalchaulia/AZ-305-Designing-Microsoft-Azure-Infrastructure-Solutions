# Instructions

## Exercise 3: Add App Registration for Access via Apps.

In this exercise you are going to register an application with Azure Active Directory, which enables a user with Power Apps user account to connect to their Microsoft Dataverse environment from client applications using OAuth authentication.

In this exercise, you will:

+ Task 1: Create an application registration.

### Estimated Timing: 30 minutes

### Task 1: Create an application registration

App registration is a way to reserve an application in AAD (Azure Active Directory), to integrate an application with Azure, you must register it in the App Registration.

In this task you are going to create an application registration.

#### Steps:

1. In the Azure portal, go to **Active Directory**, then select **App registrations**, then select **+ New registration**.

    ![img](../media/appr1.png)

2. In the **Register an application** page, enter your application's registration information:

    | Section | Values |
    | ------- | ------ |
    | Name | **contosoapp-test** |
    | Supported account types | Select **Accounts in this organizational directory only** |
    | Redirect URI (optional) | Select **Web** and enter **https://contosoapp-test.com** |
    
3. Select **Register** to create the application. 

    ![img](../media/appr2.png)
    
4. On the **Overview** section of **contosoapp-test**, select **Application ID URI**.

    ![img](../media/appr3.png)

5. Select **+ Add scope**.

    ![img](../media/appr4.png)

6. On the **Add a scope** side screen please enter the following information:
  
    | Section | Values |
    | ------- | ------ |
    | Scope name | **scope1** |
    | Who can consent? | Select **Admins and Users** |
    | Admin consent display name | **View user files** |
    | Admin consent description | **Allows app to view theuser details** |
    | State | **Enabled** |
   
    ![img](../media/appr5.png)

7. Once the **Scope** is added, go to **Active Directory**, then select **App registrations**. Select the **contosoapp-test**.

    ![img](../media/appr6.png)

9. Select **Manifest** tab, in the manifest editor, set the **allowPublicClient** property to **true** and click on **Save**.

    ![img](../media/appr7.png)

10. Select **API permissions** tab, click on **Add a permission**.

    ![img](../media/appr8.png)

11. On the **Request API permission**, please select **APIs my organization uses**, then search **dataverse** on the search bar, select **Dataverse**.

    ![img](../media/appr9.png)

12. Select **Delegated permissions** and check the **user_impersonation** option and click on **Add permissions**.

    ![img](../media/appr10.png)

This completes the registration of your application in Azure Active Directory.

#### Review

In this lab, you have:

- Created an application registration.














