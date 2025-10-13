---
lab:
    task: 'Create a data loss prevention (DLP) policy'
    exercise: 'Exercise 3 - Create a data loss prevention (DLP) policy'
---

# Skilling Tasks

**Tasks**:

1. Create a DLP policy in simulation mode
1. Modify a DLP policy
1. Create a DLP policy in PowerShell
1. Activate a policy in simulation mode

## Task 1 – Create a DLP policy in simulation mode

In this exercise, you'll create a data loss prevention (DLP) policy to protect sensitive data from being shared by users. The DLP policy that you create will inform your users if they want to share content that contains credit card information and allow them to provide a justification for sending this information. The policy will be implemented in simulation mode because you don't want the block action to affect your users yet.

1. In **Microsoft Edge**, navigate to **`https://purview.microsoft.com`** and log into the Microsoft Purview portal as the user you selected to have **Compliance Administrator** rights.

1. Select **Solutions** from the left sidebar, then select **Data Loss Prevention**.

1. On the left sidebar, select **Policies**.

1. On the **Policies** page, select **+ Create policy** to start the configuration for creating a new data loss prevention policy.

1. On the **Start with a template or create a custom policy** page, select **Custom** as the category, then select **Custom policy** under **Regulations**.

1. Select **Next**.

1. On the **Name your DLP policy** page enter:

   - **Name**: `Credit Card DLP Policy`
   - **Description**: `Protect credit card numbers from being shared`

1. Select **Next**.

1. On the **Assign admin units** page select **Next**.

1. On the **Choose locations to apply the policy** page, enable the location for **Teams chat and channel messages** only. If any other locations are selected, deselect them.

1. Select **Next**.

1. On the **Define policy settings** page, select **Create or customize advanced DLP rules**, then select **Next**.

1. On the **Customize advanced DLP rules** page, select **+ Create rule**.

1. On the **Create rule** flyout page, enter `Credit card information` as name in the **Name** field.

1. Under **Conditions**, select **+ Add Condition**, then select **Content contains**.

1. In the new **Content contains** area, select **Add**, then select **Sensitive info types**.

1. On the **Sensitive info types** page, select **Credit Card Number** then select **Add**.

1. Select **+ Add condition**, then select **Content is shared from Microsoft 365**.

1. In the new **Content is shared from Microsoft 365** section, select the **only with people inside my organization** option.

1. Under **Actions** select **+ Add an action**, then select **Restrict access or encrypt the content in Microsoft 365 locations**.

1. In the new **Restrict access or encrypt the content in Microsoft 365 locations** area select **Block everyone.**

1. Under **User notifications**, turn **On** the option for **Use notifications to inform your users and help educate them on the proper use of sensitive info.**, then select the checkbox to **Notify users in Office 365 service with a policy tip**.

1. Under **User overrides** select the checkbox to **Allow users to override policy restrictions Fabric (including Power BI), Exchange, SharePoint, OneDrive and Teams.**

1. Select the checkbox to **Require a business justification to override**.

1. Under **Incident reports**, in the **Use this severity level in admin alerts and reports** dropdown, select **Low**.

1. At the bottom of the **Create rule** flyout panel, select **Save**.

1. Back on the **Customize advanced DLP rules**, select **Next**.

1. On the **Policy mode** page select **Run the policy in simulation mode** and select the checkbox for **Show policy tips while in simulation mode**.

1. Select **Next**.

1. On the **Review and finish** page review your settings then select **Submit**.

1. On the **New policy created** page select **Done**.

You have now created a DLP policy that scans for credit card numbers in Microsoft Teams chats and channels, allowing users to provide a business justification to override the policy.

## Task 2 – Modify a DLP policy

In this task, you'll modify the existing DLP policy created in the previous task to also scan emails for credit card information. This modification ensures that sensitive data is protected across more communication channels.

1. You should still be logged into Microsoft 365 as the user you selected to be your **Compliance Administrator**.

1. You should still be on the **Policies** page in Microsoft Purview. If not, open **Microsoft Edge** and navigate to `https://purview.microsoft.com`. Select **Solutions** > **Data Loss Prevention** > **Policies**.

1. On the **Policies** page select the checkbox for the recently created **Credit Card DLP Policy**, then select **Edit policy** to open the policy configuration.

1. On the **Name your DLP policy** page, select **Next**.

1. On the **Assign admin units** page select **Next**.

1. On the **Choose locations to apply the policy** page, select the checkbox for **Exchange email** to add this location to your DLP policy.

1. Select **Next** until you reach the **Review and finish** page.

1. Select **Submit** on the **Review and finish** page to apply the change you made to the policy.

1. Once the policy is updated select **Done** on the **Policy updated** page.

You have successfully modified the DLP policy to include email scanning, enhancing the protection of sensitive information.

## Task 3 – Create a DLP policy in PowerShell

In this task, you'll use PowerShell to create a DLP policy to protect Contoso employee IDs and prevent them from being shared via Exchange. This policy will notify users attempting to share this sensitive data and block the email if it contains Employee IDs.

1. On your desktop, open an elevated PowerShell window by right clicking the Windows button in the task bar, then select **Terminal (Admin)**.

1. Run the **Install Module** cmdlet in the terminal window to install the latest **Exchange Online PowerShell** module version:

    ```powershell
    Install-Module ExchangeOnlineManagement
    ```

1. Confirm the Untrusted repository security dialog with **Y** for Yes and press **Enter**.  This process may take some time to complete.

1. Run the **Connect-IPPSSession** cmdlet to connect to the Security & Compliance PowerShell:

   ```powershell
   Connect-IPPSSession
   ```

1. Sign in as the user you selected as your **Compliance Administrator** in the **Sign in to your account** pop-up window.

1. Run the **New-DlpCompliancePolicy** cmdlet to create a DLP policy that scans all Exchange mailboxes:

   ```powershell
   New-DlpCompliancePolicy -Name "EmployeeID DLP Policy" -Comment "This policy blocks sharing of Employee IDs" -ExchangeLocation All
   ```

1. Run the **New-DlpComplianceRule** cmdlet to add a DLP rule to the DLP policy you created in the previous step:

   ```powershell
   New-DlpComplianceRule -Name "EmployeeID DLP rule" -Policy "EmployeeID DLP Policy" -BlockAccess $true -ContentContainsSensitiveInformation @{Name="Contoso Employee IDs"}
   ```

1. Run the **Get-DLPComplianceRule** cmdlet to review the **EmployeeID DLP rule**:

   ```powershell
   Get-DLPComplianceRule -Identity "EmployeeID DLP rule"
   ```

You have successfully created a DLP policy using PowerShell that scans for Contoso Employee IDs in Exchange.

## Task 4 – Activate a policy in simulation mode

In this task, you'll activate the **Credit Card DLP Policy** you created in simulation mode so it enforces its protective actions.

1. You should still be logged into Microsoft 365 as the user you selected as your **Compliance Administrator**.

1. In **Microsoft Edge**, navigate to DLP policies by going to `https://purview.microsoft.com` > **Solutions** > **Data Loss Prevention** then select **Policies** from the left sidebar.

1. On the  **Policies** page select the checkbox for the **Credit Card DLP Policy** and select **Edit policy** to open the policy configuration.

1. Select **Next** until you reach the **Policy mode** page and select **Turn the policy on immediately**.

1. On the **Review and finish** select **Submit**.

1. On the **Policy updated** page select **Done**.

You have successfully activated the DLP policy, ensuring that any attempts to share credit card information are blocked and require a business justification.
