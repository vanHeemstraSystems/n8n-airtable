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

Although there is no visible output, we can still conclude that the workflow **Activity Management**n was successfully triggered by our workflow **Activity API Management** as the executions of the workflow **Activity Management** has increased by one:

![Screenshot 2024-07-09 at 16 52 45](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/b5d3da5b-6223-4ca0-b1da-d03c6e8db0bd)

Next, let's trigger the workflow **Activity Data Management** from the workflow **Activity Management** to store the values.

In the workflow **Activity Management** add an **Execute Workflow** node.

![Screenshot 2024-07-09 at 16 58 56](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/7cb5350a-c2ec-40d9-b6be-f75ab2882b39)

Choose **Call Another Workflow**.

![Screenshot 2024-07-09 at 17 01 17](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/4c61c1d3-899c-4014-be0b-71327e175ab4)

Configure the *outgoing* **Execute Workflow** node as follows:

![Screenshot 2024-07-09 at 17 03 11](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/a308032d-41ba-4627-94c7-0ae73057b4fb)

**Note**: For the source we choose the n8n Database itself, where it keeps record of all its workflows. The Worflow ID is a copy of the end of the direct URL (here: https://wvanheemstra.app.n8n.cloud/workflow/OICEEpfNhsv5uytm) to the **Activity Data Management Workflow**. Also, we choose to **Run once with all items**.

Instead of having to go back to the parent workflow **Activity API Management**, we can make use of the INPUT option to Execute the workflow right there. Let's do so. Click **Execute Previous nodes**.

![Screenshot 2024-07-09 at 17 10 23](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/17967d4d-b44d-4397-9e7c-8408092b944a)

As the previous node was *empty*, the test ran but output was generated. That is OK, let's move on. **Save** the changes to the workflow **Activity Management**.

**IMPORTANT**: As the latest data has not yet been showing up in the INPUT side of the **Airtable** node of the workflow **Activity Data Management**, execute the INPUT to watch the latest data being displayed:

```
Activity ID: 2
Activity Name: Commute
Activity Status: Done
```

![Screenshot 2024-07-11 at 13 06 06](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/8486466a-9fc5-49c4-85fb-feb3b4768484)

As we will be sourcing our data from the workflow **Activity API Management**, we remove the **Edit Fields** node from the workflow **Activity Data Management** as follows:

![Screenshot 2024-07-11 at 14 01 11](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/ca1914f4-6c8e-403d-84ec-5655844226fd)

The **Airtable** node in the workflow **Activity Data Management** now looks like this:

![Screenshot 2024-07-11 at 14 07 07](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/af4c27d0-f885-4676-b145-2969e26ef54c)

Where **Mapping Column Mode** is now set to **Map Automatically**.

We will go back all the way to the workflow **Activity API Management**. 

**IMPORTANT**: As the latest data has not yet been showing up in the INPUT side of the **Execute Workflow** node of the workflow **Activity API Management**.

![Screenshot 2024-07-11 at 13 18 56](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/b9437934-5710-47dd-a695-962ab47bd746)

Execute the INPUT by clicking **Execute previous nodes** to watch the latest data being displayed:

```
Activity ID: 3
Activity Name: Breakfast
Activity Status: Not Started
```

![Screenshot 2024-07-11 at 13 24 32](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/25d3b95b-5193-4a1a-83a0-efff2c1642a8)

From here we run a **Test step** from within the **Execute Workflow** node.

![Screenshot 2024-07-11 at 13 56 12](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/ef2f7349-d39d-45c3-9dcc-c073b14bfd3c)

You can see that the OUTPUT values are as expected:

```
Activity ID: 3
Activity Name: Breakfast
Activity Status: Done
```

Furthermore, looking into the database, we see that the values have been correctly entered:

![Screenshot 2024-07-11 at 13 57 55](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/44f9d9dd-e399-4920-a803-945dd95a49cd)

In order to execute our workflows from over the (Inter-)network, we'll connect first of all our **Change_Status** API node to the **Execute Workflow** node (parallell to the **Edit Fields** node) in the workflow **Activity API Management**. See below:

![Screenshot 2024-07-11 at 14 14 46](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/3ce65d5c-afb8-4892-80f3-28fa88b535ab)

Make sure to **Save** the changes to the workflow!

Recap the settings inside the **Change_Status** node as being:

![Screenshot 2024-07-11 at 14 18 59](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/8a8f93c2-e9b3-4fc9-9f1e-de4219270eb9)

In order to test calling this **Change_Status** API, we''ll switch to the **Production URL**.

In **[Postman](https://learning.postman.com/docs/getting-started/installation/installation-and-updates/)**, enter the below URL in a POST request:

```
https://wvanheemstra.app.n8n.cloud/webhook/api/v1/activity/change_status
```

![Screenshot 2024-07-11 at 14 39 43](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/9f939e8d-48b4-478a-a582-4770038447fc)

In the body of the **POST** request are the parameters in JSON format:

```
{
  "Activity ID": 3,
  "Activity Name": "Breakfast",
  "Activity Status": "In Progress"
}
```

Click **Send** in Postman to submit the request to our Production URL of n8n.

![Screenshot 2024-07-11 at 14 46 57](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/d150ebee-c82a-462e-8444-8f71d2918028)

We have received a warning ```Authorization data is wrong!```.

Let's set up the right Authorization in Postman as follows:

== IMAGE GOES HERE ==  

MORE
