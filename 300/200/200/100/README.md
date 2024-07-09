# 100 - Create a sub workflow in n8n

In n8n, create a new workflow and name it **Activity Management**.

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

![Screenshot 2024-07-09 at 15 56 20](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/6a762e64-bce4-44d2-90b6-414f06c0bff2)

**Note**: The Worflow ID is a copy of the end of the direct URL to the **Activity Management Workflow**. Also, we choose to **Run once with all items**.

Try it, by clicking **Test step**.


