# 100 - Create a sub workflow in n8n

In n8n, create a new workflow and name it **Activity Management**. *This will become a sub workflow of **Activity API Management**.*

![Screenshot 2024-07-09 at 15 44 30](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/2b42d94f-df1c-404c-b1b1-52e752b21e32)

Choose **When called by another workflow** as the new step to be added to the empty composition workflow.

![Screenshot 2024-07-09 at 15 40 04](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/15d7b868-000b-4587-82d3-12b3760a75c6)

This is the dialog for this step.

![Screenshot 2024-07-09 at 15 41 41](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/564a4993-539c-4d01-bc23-59281a27ec79)

Exit the dialog, but don't forget to **Save** it.

For now let us head back to a previously created workflow **Activity API Management***.

![Screenshot 2024-07-09 at 15 49 52](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/09fd3e1a-d05e-44f1-baaa-9155bdebb4ae)

Choose to add a new node of type **Execute Workflow**.

![Screenshot 2024-07-09 at 15 52 11](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/c17bab8c-0669-4916-bb4a-331f170ec17f)

Next, choose **Call Another Workflow**.

![Screenshot 2024-07-09 at 16 23 21](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/26fcbbca-93d6-4511-9aec-c4da32102c70)

**Note**: For the source we choose the n8n Database itself, where it keeps record of all its workflows. The Worflow ID is a copy of the end of the direct URL (here: https://wvanheemstra.app.n8n.cloud/workflow/HjExDX7NwHJTSTVg) to the **Activity Management Workflow**. Also, we choose to **Run once with all items**.

Try it, by clicking **Test step**.

As a temporary solution, add a **Edit Fields** node to the **Activity API Management** node. 

![Screenshot 2024-07-09 at 16 32 52](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/294c749a-d63c-4026-817f-c4e54c31a625)

Created the familiar three fields:

- **Activity ID** = 3
- **Activity Name** = Breakfast
- **Activity Status** = Not Started

![Screenshot 2024-07-09 at 16 39 53](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/08057786-5aed-4124-aa52-199b5748f552)

Try it, by clicking **Test step**.

![Screenshot 2024-07-09 at 16 41 17](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/107d2720-484c-4977-b958-13e057d13db4)

Connect the **Edit Fields** node to the **Execute Workflow** node by dragging the line from the **Edit Fields** node to the **Execute Workflow** node.

![Screenshot 2024-07-09 at 16 43 06](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/9d1ac35a-4c5e-443c-9a85-06c0687f0f57)

Don't forget to **Save** the workflow.

Open the **Execute Workflow** node and run the **Test step**.

![Screenshot 2024-07-09 at 16 49 00](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/142086f2-3984-4833-b18b-520f1ce80a1d)

You'll see that the values have been forwarded, to end up at the workflow **Activity Management**.


MORE
