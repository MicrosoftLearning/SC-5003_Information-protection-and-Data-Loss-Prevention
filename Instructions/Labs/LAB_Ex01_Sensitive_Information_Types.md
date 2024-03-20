---
lab:
    task: 'Create a custom sensitive information type'
    exercise: 'Exercise 1 - Create a custom sensitive information type'
---

## WWL Tenants - Terms of use

If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training.

Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and are not eligible for extension.

Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time.

# Skilling tasks

Your task is to create a custom sensitive information type (SIT) that meets the required criteria:

- **Custom regex pattern for employee ID**: Include a regex pattern that identifies your organization's unique employee ID configuration, which consists of 9 characters: 3 digits, a dash, followed by 5 letters (e.g., 123-abcde).
- **Keyword list associated with employee IDs**: Incorporate a list of keywords that are commonly associated with employee IDs to enhance detection accuracy.

## Task 1 - Create a sensitive info type

1. Navigate to the Microsoft Purview Compliance Portal.
1. Expand **Data classification** then select **Classifiers**.
1. Select **Sensitive info types** then select **+ Create sensitive info type**.
1. On the **Name your sensitive info type** page give your sensitive info type a meaningful **Name** and **Description**, then select **Next**.
1. On the **Define patterns for this sensitive info type** page, select **Create pattern**.
1. On the **New pattern** page select **+ Add primary element** > **Regular expression**.
1. On the **Add a regular expression page**, give the regular expression a meaningful name for **ID** and enter `\d{3}-[a-zA-Z]{5}` in the **Regular expression** field to support the organization's requirement. Select **Done** once complete.
1. Back on the **New pattern** page under **Supporting elements** select **+ Add supporting elements or group of elements** > **Keyword list**.
1. On the **Add a keyword list** page, give your keyword list a meaningful **ID**. In **Keyword group #1** under **Case insensitive** enter:
   - `Employee ID`
   - `Staff number`
   - `Work ID`
1. Select **Done** once complete.
1. Back on the **New pattern** page select **Create**.
1. Select **Next** on the **Define patterns for this sensitive info type** page.
1. On the **Choose the recommended confidence level to show in compliance policies** page, leave the default select, then select **Next**.
1. Review your settings, then select **Create**.
1. On the **Your sensitive info type is created** page, select **Done**.

You have now successfully created a custom sensitive information type (SIT) to improve the security and management of your company's unique employee ID numbers.
