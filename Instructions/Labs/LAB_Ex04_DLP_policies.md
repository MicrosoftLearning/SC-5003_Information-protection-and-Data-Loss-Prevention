---
lab:
    task: 'Create a data loss prevention (DLP) policy'
    exercise: 'Exercise 4 - Create a data loss prevention (DLP) policy'
---

# Skilling Tasks

Your task is to develop and enforce a custom data loss prevention (DLP) policy tailored to secure your organization’s sensitive customer data, while also ensuring compliance with data protection regulations.

- **Create a custom DLP policy** in test mode to monitor data without enforcement.
- **Define an advanced DLP rule** targeting specific sensitive information.
- **Activate the DLP policy** to enforce protections and compliance actively.

**Objective**: Develop and implement a custom Data Loss Prevention (DLP) policy to safeguard sensitive customer data and ensure regulatory compliance. You will start by creating a DLP policy in test mode for initial monitoring, proceed to design an advanced rule targeting specific types of sensitive information, and finally, activate the policy to enforce data protection across email, SharePoint, OneDrive, and Teams communications.

## Task 1 - Create a custom data loss prevention (DLP) policy

1. Navigate to the Microsoft Purview Compliance Portal.
1. Expand **Data loss prevention** then select **Policies**.
1. On the **Policies** page, select **+ Create policy**.
1. In the DLP policy wizard, on the **Start with a template or create a custom policy** select:
   - Categories: **Custom**
   - Regulations: **Custom policy**
1. Select **Next**.
1. On the **Name your DLP policy** page enter:
   - **Name**: `Customer interaction protection policy`
   - **Description**: `This DLP policy protects customer data integrity and confidentiality in the Customer Service department by preventing unauthorized access and disclosure.`
1. Select **Next** until you reach the **Choose where to apply the policy** page.
1. On the **Choose where to apply the policy** page select only:
   - **Exchange email**
   - **SharePoint sites**
   - **OneDrive accounts**
   - **Teams chat and channel messages**
1. Select **Next**.
1. On the **Define policy settings** page, select **Create or customize advanced DLP rules**, then select **Next**.
1. On the **Customize advanced DLP rules** select **+ Create rule**.
1. On the **Create rule** page:
   - In the **Name** field enter `Customer data`.
   - Under **Conditions** select **+ Add condition** > **Content contains**.
   - Under **Content contains** select **Add** > **Sensitive info types**.
   - On the **Trainable classifiers** page on the right, select the classifiers for `Customer Complaints` and `Customer Files`, then select **Add** at the bottom of the page to add these pretrained classifiers.
   > [!tip] Use the search bar to easily find trainable classifiers.
   - Back on the **Create rule** page under **Content contains** select **+ Add condition** > **Content is shared from Microsoft365**.
   - Under **Content is shared from Microsoft365** select **with people outside my organization** from the dropdown.
   - Under **Actions** select **+ Add an action** > **Restrict or encrypt the content in Microsoft 365 locations**.
   - Under **Restrict or encrypt the content in Microsoft 365 locations** ensure the radio button for **Block only people outside your organization** is selected.
   - Under **User notifications** toggle notifications **On**, then select the checkbox to **Notify users in Office 365 service with a policy tip**.
   - Under **User overrides** select the checkbox for **Allow overrides from Microsoft 365 services**
   - Under **Incident reports** set the **Use this severity level in admin alerts and reports:** to **Medium**.
   - At the  bottom of the **Create rule** select **Save**.
1. Back on the **Customize advanced DLP rules** page, select **Next**.
1. On the **Policy mode page** select **Run the policy in test mode** and ensure the **Show policy tips while in simulation mode** option is enabled, then select **Next**.
1. On the **Review and finish** page select **Submit**.
1. On the **New policy create** page select **Done**.

## Task 2 - Modify a DLP policy

1. On the **Policies** page, select the checkbox to the left of the newly created **Customer interaction protection policy** policy, then select **Edit policy** at the top of the page.
1. Once in the DLP policy creation wizard, select **Next** until you reach the **Policy mode** page, then select **Turn the policy on immediately** to enforce the DLP policy.
1. Select **Next** to review the DLP policy, then select **Submit** once you've reviewed your changes.
1. On the **Policy updated** page select **Done**.

You have now successfully created a DLP policy to protect sensitive customer data.
