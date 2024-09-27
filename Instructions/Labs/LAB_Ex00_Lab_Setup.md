---
lab:
    title: 'Lab Setup: Preparing Your Environment for Administration'
    module: 'Module 0 - Lab Setup'
---

## WWL Tenants - Terms of use

If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training.

Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and are not eligible for extension.

Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time.

# Lab Setup: Preparing Your Environment for Administration

In this lab, you'll configure and prepare your environment for administration tasks. You'll activate necessary features, set up administrative permissions, and ensure proper configuration of key elements.

**Tasks:**

- Enable Audit in the Microsoft Purview portal
- Enable Search by Name in Microsoft Teams
- Enable information barriers in SharePoint Online and OneDrive

## Task - Enable Audit in the Microsoft Purview portal

In this task, you'll enable Audit in the Microsoft Purview portal to monitor portal activities.

1. In Microsoft Edge, navigate to the Microsoft Purview portal, `https://purview.microsoft.com`, and log in as a user with **Global Administrator** rights.

1. A message about the new Microsoft Purview portal will appear on the screen. Select the option to agree with the terms of data flow disclosure and the privacy statement, then select **Try now**.

    ![Screenshot showing the Welcome to the new Microsoft Purview portal screen.](../Media/welcome-purview-portal.png)

1. Select **Solutions** from the left sidebar, then select **Audit**.

1. On the **Search** page, select the **Start recording user and admin activity** bar to enable audit logging.

    ![Screenshot showing the Start recording user and admin activity button.](../Media/enable-audit-button.png)

1. Once you select this option, the blue bar should disappear from this page.

You have successfully enabled auditing in Microsoft 365.

## Task – Assign compliance roles

In this task, you'll assign the Compliance Admin to the user you'll be using for these lab exercises.

1. Open **Microsoft Edge** and navigate to the Microsoft Purview portal, `https://purview.microsoft.com`. You'll need to login as a user that has **Global Administrator** rights.

1. Select **Settings** from the left sidebar.

1. On the left sidebar, expand **Roles and scopes** then select **Role groups**.

1. On the **Role groups for Microsoft Purview solutions** select **Compliance Administrator**.

1. On the **Compliance Administrator** flyout panel on the right, select **Edit** to edit this role group.

1. On the **Edit members of the role group** page, select **Choose users**.

1. On the **Choose users** flyout panel on the right, select the checkbox to the left of the user you'll be performing the next lab exercises with, then select the **Select** button at the bottom of the page.

1. Back on the **Edit members of the role group** page, select **Next**.

1. On the **Review the role group and finish** page, review your changes and select **Save**.

1. On the **You successfully updated the role group** select **Done**.

1. Sign out of the account with the Global Administrator rights by selecting their user icon in the top right, then selecting **Sign out**.

   Example:

   ![Screenshot showing the navigation path to sign out of the MOD Administrator account.](../Media/sign-out.png)

You have successfully assigned a user the Compliance Administrator role, which is required to perform the different exercises of this lab.

## Task – Explore the Microsoft Purview portal

In this task, you'll sign in as the user you previously granted **Compliance Administrator** role to explore the Microsoft Purview portal. This role will be referred to as your **Compliance Administrator** in the next labs and exercises.

1. In **Microsoft Edge**, navigate to **`https://purview.microsoft.com`**.

1. When the **Pick an account** window is displayed, select **Use another account**.

1. When the **Sign in** window is displayed, sign in as the user you previous selected as the **Compliance Administrator**.

1. Get yourself familiar with the new Microsoft Purview Portal. When you are done, leave the browser window open.

You have successfully switched to the **Compliance Administrator**'s account and are now ready to start the lab.
