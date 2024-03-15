---
lab:
    task: 'Create and publish a sensitivity label'
    exercise: 'Exercise 2 - Create and publish a sensitivity label'
---

# Skilling Tasks

Your task is to create and publish sensitivity labels within your organization that  classifies and protects sensitive data according to its level of confidentiality and the necessary access controls.

- **Create an _Internal_ sensitivity label**: Create a sensitivity label called _Internal_ to categorize all data that is only for internal use.
- **Create _Employee Data (HR)_ sublabel**: Under the _Internal_ label, create a sublabel named _Employee Data (HR)_ dedicated to the Human Resources department's sensitive information.

### Test your skills by following the challenge before viewing the exercise instructions.

### Challenge: Implement Sensitivity Labels for HR Department

**Objective**: Create and publish a sensitivity label to improve data protection in the HR department. Your task is to set up a main sensitivity label called _Internal_, with a sublabel under it called _Employee Data (HR)_. This classification system should follow these criteria to ensure effective data protection and compliance:

- The labels should permit access to any authenticated user, ensuring that only verified individuals can view the sensitive data.
- Facilitate offline access to the labeled data for a period of 14 days, supporting operational flexibility while maintaining security protocols.
- Set the user access to the labeled data to never expire, ensuring persistent protection of the information over time.
- Create a policy named _Internal HR employee data_ that requires users to provide a justification for removing a label or lowering it classification.

By applying these labels correctly, you will help to ensure the safe management of confidential HR documents, in accordance with the organization's data protection objectives.

### Exercise instructions

## Task 1 instructions - Create a sensitivity label

1. Navigate to the Microsoft Purview Compliance Portal.
1. Expand **Information protection**, then select **Labels**.
1. On the **Labels** select **+ Create a label**.
1. On the  **Provide basic details for this label** enter the following information:

    - **Name**: `Internal`
    - **Display name**: `Internal`
    - **Description for users**: `Internal sensitivity label.`
    - **Description for admins**: `Internal sensitivity label for Contoso.`

1. Select **Next**.
1. On the **Define the scope for this label** page, select **Items** and select **Files** and **Emails** then select **Next**.
1. On the **Choose protection settings for the types of items you selected** page, select **Next**.
1. Select **Next** and accept defaults until you reach the **Review your settings and finish** page select **Create label**.
1. On the **Your sensitivity label was created** page, select **Don't create a policy yet**, then select **Done**.

## Task 2 instructions - Create a sublabel label

1. On the Information protection page, highlight (without selecting) the newly created **Internal** label and select the vertical **...**
    ![Image of vertical dot menu](../Media/SensitivityLabelDotMenu.png)
1. Select the **+ Create sublabel** from the menu.
1. On the  **Provide basic details for this label** enter the following information:

   - **Name**: `Employee data (HR)`
   - **Display name**: `Employee data (HR)`
   - **Description for users**: `This label is the default label for all documents in the HR Department.`
   - **Description for admins**: `This label is created in consultation with the Director of HR.`
1. Select **Next**.
1. On the **Define the scope for this label** page, select **Items** and select **Files** and **Emails** then select **Next**.
1. On the **Choose protection settings for the types of items you selected**, select the checkbox for **Control access**, then select **Next**.
1. On the **Access control** page:
   - Ensure the radio button for **Configure access control settings** is selected.
   - Under **Assign permissions now or let users decide?** select **Assign permissions now**.
   - Under **User access to content expires** select **Never**.
   - Under **Allow offline access** select **Only for a number of days**.
   - In the **Users have offline access to the content for this many days** field input 14.
   - Under **Assign permissions to specific users and groups** select the **Assign permissions** button.
1. On the **Assign permissions** page, select **+ Add any authenticated users**, then select **Save**.
1. Back on the **Access control** page select **Next**.
1. Select **Next** and accept defaults until you reach the **Review your settings and finish** page select **Create label**.
1. On the **Your sensitivity label was created** page, select **Don't create a policy yet**, then select **Done**.

## Task 3 instructions - Publish a sensitivity label

1. On the **Labels** page, select the checkboxes next to the newly created **Internal** and the **Employee data (HR)** sublabel.
1. On the **Choose sensitivity labels to publish** page, ensure both the Internal and Employee data (HR) labels are displayed under **Sensitivity labels to publish**, then select **Next**.
1. Select **Next** until you reach the **Policy settings** page.
1. On the **Policy settings** page select the checkbox for **Users must provide a justification to remove a label or lower its classification**.
1. Select **Next** until you reach the **Name your policy** page
1. On the **Name your policy** page, enter the following information:

   - **Name**: `Internal HR employee data`
   - **Enter a description for your sensitivity label policy**: `This HR label is to be applied to internal HR employee data.`

1. Select **Next**.
1. On the **Review and finish** page select **Submit**.
1. On the **New policy created** page select **Done**.

You have now successfully created a sensitivity label to classify employee data for the HR department.
