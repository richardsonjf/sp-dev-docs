---
title: Send an email when a new item is created or modified in a SharePoint list
description: Send an email when a new item is created or modified in a SharePoint list
ms.date: 12/12/2018
ms.prod: sharepoint
localization_priority: Priority
---

# Send an email when a new item is created or modified in a SharePoint list

Using Power Automate, you can easily automate day-to-day tasks or build repetitive tasks in SharePoint that help you stay productive.

In this tutorial, you will create a flow that sends an email when a new item is added or modified in a SharePoint list.

## Required setup

Before proceeding with these instructions, make sure your SharePoint site is set up with the required lists and libraries.

## Create a flow

1. In your SharePoint site, browse to the **Projects** list.

2. To create and manage flows for a list or a library, from the command bar, on the list or library page, select **Automate** > **Power Automate**. Selecting **Power Automate** expands to show you more options:

    * Create a flow
    * See your flows
    * Configure flows

    > **Note:** If they are available for the list or library here, you may see other options such as **Set a reminder** and other flows.

    ![Create a flow from Projects list](../../../images/gs01-create-a-flow-command-bar.png)

3. Select **Create a flow**. In the **Create a flow** panel, you can explore various templates available for your list.

    ![Create a flow panel in lists](../../../images/gs01-create-a-flow-panel.png)

4. Select the template that reads:
    > Send a customized email when a new SharePoint list item is added.

   On a new browser tab, the **Power Automate** website appears and displays:
      * Template information
         * Name and description of the template.
      * Connection information
         * Varioius services this flow connect to.
         * The credentials those services will use to connect to.
         
5. Using the dropdowns, verify the connection information (**SharePoint Site Address** and **SharePoint List Name**) is accurate to ensure it uses your credentials.
    > A green checkmark icon indicates a connection to the service was succesfully made using your credentials.

    ![Flow template - send email when an item is added in a list](../../../images/gs01-create-a-flow-when-item-is-added-template.png)

6. To create the flow, select **Create Flow**. Any connections that require a connection is also attempted during this step. After the flow is created successfully, you are redirected to the flow designer where you can edit and modifify the flow if needed.

    ![Flow designer - send email when an item is added in a list](../../../images/gs01-designer-when-item-is-added-template.png)

7. Select the name of the flow that reads **Send a customized email when a new SharePoint list item is added**, and enter the following name for the flow:
    * Send an email for new projects

   The SharePoint actions are represented with the SharePoint logo in the flow designer.

8. In the **When the new item is created** action, to expand the action, select **Edit**. Note the input configured to the SharePoint site address and list name from where you created the flow.

9. In the **Send Email** action, to expand the action, select **Edit**. All the input is filled in with dynamic values from the **Get my profile** and **When the new item is created** actions.

10. Hover over the dynamic values to see what properties they reference. For example, hovering over **Email** shows that the property is read from the **Mail** property in **Get my profile**.

    ![Flow designer - hover to see dynamic content](../../../images/gs01-designer-hover-dynamic-content.png)

11. To save the flow, select **Save**.

Your flow is active as soon as you save the flow. In this case, this flow **Send an email for new projects** is now active, and runs whenever new items are added to the **Projects** list in the specified SharePoint site.

## Test your flow

To test your flow, either add a new item in SharePoint list by adding a new item, or initiate the test run directly from the flow designer. To test the flow from the designer, follow these steps. Testing the flow from the designer helps you to quickly see the flow run as the flow is executed.

1. In the flow designer, on the top command bar, select **Test**.

2. In the **Test Flow** panel, select **I'll perform the trigger action**, and then select **Save & Test**.

    ![Flow designer - hover to see dynamic content](../../../images/gs01-designer-test-flow.png)

   A message appears instructing you to add a new list item to the SharePoint list you selected.

    ![Flow designer - test flow message](../../../images/gs01-designer-test-flow-message.png)

3. You should have the browser tab with the **Projects** list opened already. If not, open a new browser tab, and browse to the **Projects** list.
    > Do not close the flow designer. Make sure you keep the flow designer browser tab open.

4. In the **Projects** list, on the command bar, select **New**, and add the following items, and then select **Save**:
    * Title: Project 4
    * Owner: Select a user from people picker

5. Switch to the flow designer tab. The flow run history appears. If all of your actions were executed successfully, a green checkmark icon appears aside every action.

    ![Flow designer - flow run history](../../../images/gs01-designer-test-flow-run.png)

6. Select the action to see the inputs and outputs used in the flow run. This is also a good place to see the actual values translated from those dynamic content properties used in that action.

   As a result of this flow, you receive an email regarding the new project information.

## Modify your flow

1. In the flow designer, to edit your flow, select **Edit**.

2. Select the **Send Email** action.

3. In the **Body** input, after the **Name** dynamic property, append the following string:
    * Owner:

4. While you are still editing the **Body** input, note the **dynamic content** list that appears aside the action.

5. In the **dynamic content** list, select values from the actions in your flow, (for example, in the **When the new item is created** trigger, the project owner information is available.

6. To add the owner information, in the **dynamic content** list, in the search box, search for **owner**.

    ![Flow designer - add owner dynamic content](../../../images/gs01-designer-append-owner-dynamic-content.png)

7. In the results, select **Owner DisplayName**. As you can see, it also displays other information, such as email, job title, picture and more. Because the **Owner** is a **person** column in SharePoint, SharePoint passes along the person details as individual properties to the flow.

   The modified **Body** input appears like this with the included **Owner** info.

    ![Flow designer - add owner dynamic content](../../../images/gs01-designer-email-body-with-owner.png)

8. To test the flow, repeat these steps.

   You receive an email with the updated owner information in it.

## Next steps

Congratulations on creating your first flow!

In the next topic, we will use the same flow, and add the ability to interact with Microsoft Teams.
