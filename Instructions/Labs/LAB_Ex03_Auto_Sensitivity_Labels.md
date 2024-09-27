---
lab:
    task: 'Create and assign an auto-labeling policy'
    exercise: 'Exercise 3 - Create and assign an auto-labeling policy'
---

# Skilling Tasks

Your task is to create and publish sensitivity labels within your organization that classifies and protects sensitive data according to its level of confidentiality and the necessary access controls.

1. Create a sensitivity label

## Task 1 - Create a sensitivity label

In this task, you'll create a sensitivity label that will auto label documents and emails found to contain information related to the European General Data Protection Regulation (GPDR).

1. You should still be logged into Client 1 VM (SC-400-CL1) as the **SC-400-cl1\admin** account.

1. In **Microsoft Edge**, navigate to **`https://purview.microsoft.com`** and log into the Microsoft Purview portal as **Joni Sherman**.

1. In the Microsoft Purview portal, select **Solutions** from the left side bar, then select **Information protection**. Select **Sensitivity labels**.

1. On the **Sensitivity labels** page, find the newly created **Internal** sensitivity label. Select the vertical ellipsis (**...**) next to it, then select **+ Create sublabel** from the dropdown menu.

1. The **New sensitivity label** configuration will start. On the **Provide basic details for this label** page, enter:

   - **Name**: `GDPR Germany`
   - **Display name**: `GDPR Germany`
   - **Description for users**: `This document or email contains data related to the European General Data Protection Regulation (GPDR) for the region Germany.`
   - **Description for admins**: `This label is auto applied to German GDPR documents.`

1. Select **Next**.

1. On the **Define the scope for this label** page, select **Items**, then select **Files** and **Emails**. If the checkbox for **Meetings** is selected, make sure it's deselected.

1. Select **Next**.

1. On the **Choose protection settings for labeled items** page, select **Next**.

1. On the **Auto-labeling for files and emails** page, set the **Auto-labeling for files and emails** to enabled.

1. In the **Detect content that matches these conditions** section, select **+ Add condition** > **Content contains**.

1. In **Content contains** section select the **Add** > **Sensitive info types**.

1. In the **Sensitive info types** flyout panel, search for `German` to display sensitive info types related to Germany.

1. Select the checkbox next to the **Name** field to select all sensitive info types related to German, then select **Add**.

    ![Screenshot showing how to add all German related sensitive info types.](../Media/select-all-german-types.png)

1. Back on the **Auto-labeling for files and emails** page, select **Next**.

1. On the **Define protection settings for groups and sites** page, select **Next**.

1. On the **Auto-labeling for schematized data assets (preview)** page, select **Next**.

1. On the **Review your settings and finish** page, select **Create label**.

1. On the **Your sensitivity label was created** page, select **Publish label to users' apps**, then select **Done**.

1. On the **Create auto-labeling policy** flyout panel, select **Review policy** to start the configuration to create a new label policy.

1. On the **Name your auto-labeling policy** page, enter:

   - **Name**: `GDPR Germany policy`
   - **Enter a description for your sensitivity label policy**: `This auto apply sensitivity labels policy is for the GDPR region of Germany.`

1. Select **Next**.

1. On the **Assign admin units** page, select **Next**.

1. On the **Choose locations where you want to apply the label** page, leave the defaults selected, then select **Next**.

1. On the **Set up common or advanced rules** page, select **Next**.

1. On the **Define rules for content in all locations** page, select **Next**.

1. On the **Decide if you want to test out the policy now or later** select **Run policy in simulation mode**, then select the checkbox for **Automatically turn on policy if not modified for 7 days in simulation.**, then select **Next**.

1. On the **Review and finish** page, select **Create policy**.

1. On the **Your auto-labeling policy was created** page, select **Done**.

You have successfully created and published an auto apply sensitivity label for GDPR documents in the region Germany.

It can take up to 24 hours for auto applied sensitivity labels to be applied. This duration will be longer when applied to more than 25,000 documents (that is, the daily limit).
