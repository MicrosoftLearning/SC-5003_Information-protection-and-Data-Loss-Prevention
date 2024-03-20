---
lab:
    task: 'Create and assign an auto-labeling policy'
    exercise: 'Exercise 3 - Create and assign an auto-labeling policy'
---

# Skilling Tasks

Your task is to create and publish sensitivity labels within your organization that classifies and protects sensitive data according to its level of confidentiality and the necessary access controls.

- **Create a sensitivity label** to categorize data.
- **Configure the label for auto-labeling** for files and emails.
- **Configure an auto-labeling policy** for automatically classifying data in SharePoint and OneDrive.
- **Publish the auto-labeling policy** to deploy the label across your organization, automating classification for enhanced security and compliance.

**Objective**: Create and publish an auto-labeling policy for the Finance department. Your task is to set up a sensitivity label that automatically applies labels to files and emails based on financial data. You also need to create an auto-labeling policy that automatically applies those labels to content in SharePoint and OneDrive.

## Task 1 - Create a sensitivity label

1. Navigate to the Microsoft Purview Compliance Portal.
1. Expand **Information protection**, then select **Labels**.
1. On the **Labels** select **+ Create a label**.
1. On the  **Provide basic details for this label** enter the following information:

    - **Name**: `Protected Financial Records`
    - **Display name**: `Protected Financial Records`
    - **Description for users**: `Use for documents with sensitive financial data.`
    - **Description for admins**: `Applies encryption and access controls to financial documents.`

1. Select **Next**.
1. On the **Define the scope for this label** page, select **Items** and select **Files** and **Emails** then select **Next**.
1. On the **Choose protection settings for the types of items you selected** page, select **Next**.
1. On the **Auto-labeling for files and emails**:
   - Set the toggle to enable **Auto-labeling for files and emails**
   - Under **Detect content that matches these conditions** select **+ Add condition** > **Content contains**.
   - Under **Content contains** select **Add** > **Sensitive info types**.
   - On the **Sensitive info types** page search for and add the sensitive info type for `Credit Card Number`,  `U.S. Bank Account Number`, and `ABA Routing Number`. **Add** to add the three sensitive info types, then select **Save**.
   - Under **When content matches these conditions** select **Automatically apply the label**.
   - Leave the optional **Display this message to users when the label is applied** blank.
1. Select **Next** and accept defaults until you reach the **Review your settings and finish** page select **Create label**.
1. On the **Your sensitivity label was created** page, select **Don't create a policy yet**, then select **Done**.

## Task 2 - Create an auto-labeling policy

1. On the **Labels** page, select the checkbox next to the newly created **Protected Financial Records** label and select **Create auto-labeling policy**.
1. On the **Name your auto-labeling policy** page, enter the following information:

   - **Name**: `Finance Auto-Label Policy`
   - **Enter a description for your sensitivity label policy**: `Automates the labeling of financial documents.`
1. Select **Next** until you reach the **Define rules for content in all locations** page.
1. On the **Define rules for content in all locations** select **New rule**.
1. On the **New rule** page:
   - Enter `Financial data` as the **Name**.
   - Under **Conditions** select **+ Add condition** > **Content contains**.
   - Under **Content contains** select **Add** > **Sensitive info type**.
   - On the **Sensitive info types** page search for and add the sensitive info type for `Credit Card Number`,  `U.S. Bank Account Number`, and `ABA Routing Number`. **Add** to add the three sensitive info types, then select **Save**.
1. Select **Next** until you reach the **Decide if you want to test out the policy now or later** page.
1. On the **Decide if you want to test out the policy now or later** page select **Run policy in simulation mode**, then select **Next**.
1. On the **Review and finish** page select **Create policy**.
1. On the **Your auto-labeling policy was created** page, select **Done**.

You have now successfully created a sensitivity label to classify financial data for the Finance department.
