# Instructions

## Exercise 1: Create Management Groups and assign Subscriptions

In this exercise you will create three management groups and assign subscriptions to each management groups via Azure portal.

In this Exercise, you will have:

+ Task 1: Create Management Groups.
+ Task 2: Create Child Management Groups.
+ Task 3: Assign subscriptions to management groups

## Estimated timing: 45 minutes

### Task 1: Create Management Groups

In this task, you will create a Management Group via the Azure portal.

#### Pre-requisites for this task

An Azure account. Any Azure AD user in the tenant can create a management group without the management group write permission assigned to that user if hierarchy protection isn't enabled. This new management group becomes a child of the Root Management Group or the default management group and the creator is given an "Owner" role assignment. Management group service allows this ability so that role assignments aren't needed at the root level. No users have access to the Root Management Group when it's created. To avoid the hurdle of finding the Azure AD Global Admins to start using management groups, we allow the creation of the initial management groups at the root level.

#### Steps:

1. Log into the Azure portal.

2. Select **All Services** and select **Azure Active Directory**.

   ![image](../media/man1a.png)

3. On the Azure Active Directory page, please select **Properties** under **Manage tab**, then select **Yes** for **Access management for Azure resources**, then select **Save**. 

   ![image](../media/man2a.png)

4. Please go to **Home** tab and search for **Management Groups**, then select **Management Groups** from the list.

   ![image](../media/man3.png)

5. On the Management Groups page, in the Overview section, please select the Tenant Root group.

   ![image](../media/man4.png)

6. On the Tenant Root Group page, please select **Acces Control**, then select **+ Add** and then select **Add Role Assignment**.

   ![image](../media/man5.png)

7. On the Add Role Assignment Page, please select **Owner** and select **Next**.

   ![image](../media/man6.png)

8. On the Add Role Assignment Page, under Members tab, please select **+Select members**. Then on the Select members side screen, please select the current user name and then select **Select** button.

   ![image](../media/man7.png)

9. After selecting the user, please select **Review + Assign**.

   ![image](../media/man8.png)

10. Upon assignment, you can see the current user having **Owner** role under **Access Control** section on the Tenant Root Group page. 

   ![image](../media/man9b.png)

>**Now you can create child management groups and assign subscriptions to each group**.

>**Note: The Management Group ID is the directory unique identifier that is used to submit commands on this management group. This identifier isn't editable after creation as it's used throughout the Azure system to identify this group. The root management group is automatically created with an ID that is the Azure Active Directory ID. For all other management groups, assign a unique ID.**

>**The display name field is the name that is displayed within the Azure portal. A separate display name is an optional field when creating the management group and can be changed at any time.**


### Task 2: Create Child Management Groups

In this task, you will create three management groups under the management group you have created in the previous task via Azure Portal.

#### Pre-requisites for this task

Complete Task 1.

1. On the Management Group page, please select **+ Create**

   ![image](../media/man10.png)

2. On the Create management group side screen, please enter the **Management Group ID** and **Management group display name**, then select **Submit**.

  | Settings | Values |
  |  -- | -- |
  | Management Group ID | **IT-Contoso** |
  | Management group display name* | **IT-Contoso** |

   ![image](../media/man11.png)

3. On the management groups page, overview section, you can see the newly created child management group named **IT-Contoso**.

4. Add a child group by clicking on the elipsis **(...)** on the right side of the newly created child management group named **IT-Contoso**.

   ![image](../media/man12.png)

5. On the Create management group side screen, please enter the **Management Group ID** and **Management group display name**, then select **Submit**.

  | Settings | Values |
  |  -- | -- |
  | Management Group ID | **IT-Support-c** |
  | Management group display name* | **IT-Support-c** |

   ![image](../media/man13.png)

6. By referring to step 4 and step 5, please add another child management group with the following details:

  | Settings | Values |
  |  -- | -- |
  | Management Group ID | **IT-Service-c** |
  | Management group display name* | **IT-Service-c** |

7. Expand the **IT-Contoso** management group, you can see the newly created two child management groups.

   ![image](../media/man14.png)

### Task 3: Assign subscriptions to management groups

In this task, you will assign subscriptions to the newly created management groups via Azure Portal.

#### Pre-requisites for this task

Complete Task 1 & Task 2

#### Steps:

You can add subscriptions to the management groups that you created.

1. From the Azure portal, open Management Groups and select the management group for your subscription.

2. Expand the Subscriptions under Tenant Root Group on the Mangement groups page.

   ![image](../media/man15.png)

3. Click on elipsis **(...)** on the right side of the first subscription listed, then click on **Move**.

   ![image](../media/man16.png)

4. In **Move** window, select **IT-Contoso (IT-Contoso)** management group from drop down and click on **Save**.

   ![image](../media/man17.png)

5. Add another two subscriptions to the child management groups of the **IT-Contoso** managament group by referring to step 3 & 4.

6. Expand all the child managment groups which you created in this exercise and see the subscriptions assigned to each management group.

7. In this exercise you have created three child management groups and added subscriptions to it.


#### Review

In this exercise, you have:

- Created Management Groups
- Created Child Management Groups
- Assigned subscriptions to management groups
