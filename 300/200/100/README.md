# 100 - Create a workflow in n8n

Create a new workflow **Activity Data Management** and add a **Edit Fields** node to it. We'll need the **Edit Fields** node to make sure that we send well-formatted data to the **Airtable** node.

![Screenshot 2024-07-09 at 10 25 13](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/c33c96d9-70ed-45e1-a872-58eb4e44a708)

Open the **Edit Fields** node and add three values of ```String type```. For each of these three values, do the following.

- In the **Activity ID** field, enter the same name of the column in the **Airtable** table (here: ```Activity ID```). In the **Value** field, enter a unique number (e.g. **1**).
- In the **Activity Name** field, enter the same name of the column in the **Airtable** table (here: ```Activity Name```). In the **Value** field, enter an activity name (e.g. **Lunch**).
- In the **Activity Status** field, enter the same name of the column in the **Airtable** table (here: ```Activity Status```). In the **Value** field, enter an activity status (e.g. **Not Started**).

![Screenshot 2024-07-09 at 10 29 27](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/cd5ecc53-be1d-4b3f-b60c-b1ede8ba9b5f)

Click **Test step** to verify if our entries in the form are correct.

![Screenshot 2024-07-09 at 13 33 38](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/3a8281a8-e879-48da-84e2-f3f0258885a1)

The OUTPUT side on the right shows the table with our values and column names correctly. The test ran successfully!

Close the **Edit Fields** node dialogue and confirm to save the changes. 

![Screenshot 2024-07-09 at 11 07 55](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/47fe3929-fe62-4af4-a1b7-3d93819e5110)

Now that we have structured the data in a way that would correspond to the columns in **Airtable**, let's add the **Airtable** node and connect it with the **Edit Fields** node.

![Screenshot 2024-07-09 at 11 10 49](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/15dae71b-eb65-4072-9e5f-7189ad17ac50)

When prompted, choose **Create or update a record**.

![Screenshot 2024-07-09 at 11 14 47](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/ac4cd592-a0ac-48b4-acca-0ae6cc7a080c)

Open the **Airtable** node and enter your credentials. You can find the API key by following the steps mentioned on this page: https://docs.n8n.io/credentials/airtable/.

**WARNING**: n8n previously supported an API key authentication method with Airtable. Airtable fully deprecated these keys as of February 2024. If you were using an Airtable API credential, replace it with an Airtable Personal Access Token or Airtable OAuth2 credential. n8n recommends using Personal Access Token instead.

Hence, create a Personal Access Token (PAT) in Airtable.

## Using personal access token
To configure this credential, you'll need:

- A Personal Access Token: Follow the instructions to Find/create PATs in the [Airtable documentation](https://support.airtable.com/docs/creating-personal-access-tokens#understanding-the-basics-of-personal-access-tokens) to get a Personal Access Token (PAT).
- n8n recommends using the following Scopes for your PAT:

```
data.records:read
data.records:write
schema.bases:read
```

![Screenshot 2024-07-09 at 11 27 03](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/053c59eb-543e-45e4-9553-8236a59b64e4)

Choose Developer Hub:

![Screenshot 2024-07-09 at 11 29 53](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/9633ed73-2ae7-4cad-a1c6-3a6c109610d6)

Name the Personal Access Token (PAT): **n8n_Personal_Access_Token**

For Scopes choose:

```
data.records:read
data.records:write
schema.bases:read
```

And limit your Personal Access Token to our **Activity Management** Airtable.

Click **Create token**.

![Screenshot 2024-07-09 at 11 38 40](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/33782b47-bf07-4f4c-af5a-11d46bff4639)

**WARNING**: Make sure you have copied the value of the Personal Access Token (PAT) - here masked for security reasons - somewhere safe where (only you) can retrieve it later on when it is needed!

Click **Done**.

Back in n8n, click **Select Credential** followed by **Create New Credential**.

![Screenshot 2024-07-09 at 11 50 02](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/ffe944c9-d979-4eb2-86d9-63b019bdea2b)

In the new credential dialogue, choose **Access Token** and paste the previously saved value of the Airtable Personal Access Token (```n8n_Personal_Access_Token```) in the textbox. 

![Screenshot 2024-07-09 at 11 52 27](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/109566b1-0a29-43c3-b7d4-abc84166d3dc)

Check that the scope is right and click **Save**.

Not only will the new credential be saved, but the connection (with Airtable) will also be tested.

![Screenshot 2024-07-09 at 11 57 24](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/74c4d272-8904-4cd1-934a-b55732315c94)

Luckily, the connection tested successful!

Close the new credential dialog with the **X** in the top right corner.

We'll be back at the Parameters tab:

![Screenshot 2024-07-09 at 13 38 19](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/af592a21-303b-47f0-9354-32d65ba7c1ec)

Drag the fields on the INPUT side into the values on the form.

![Screenshot 2024-07-09 at 13 41 05](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/c711d2f5-efd7-4ffb-88de-6574955f41a7)

By dragging, the values are automatically translated to JSON input parameters.

Next, click **Test step** to verify the validity of our entries.

![Screenshot 2024-07-09 at 13 44 19](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/698e2b67-d17f-40c1-9b61-bb805e56da4b)

The outcome of the test shows on the OUPUT side. The fields column lists all fields we transfered:

- Activity ID: **1**
- Activity Name: **Lunch**
- Activity Status: **Not Started**

The test took its values from the **Edit Fields** node and exported them to the **Airtable** node. The workflow is successful!

Looking into the actual table of Airtable, called **Activity Management**, we see the newly created record for our values:

![Screenshot 2024-07-09 at 13 51 09](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/994f341a-1b10-4c04-82fc-d726d3517bf6)

Source: https://airtable.com/appI63Xr8LpmGwfHa/tblYqEmioADkLmzGX/viwUlLHouucu6Bdu6?blocks=hide

**NOTE**: The empty records are a result of previous attempts to created records, when input values were still missing. These empty records can be deleted manually.
 
Lets try changing the ```Activiy Status``` in n8n from **Not Started** to **In Progress** and run our test again.

![Screenshot 2024-07-09 at 13 58 16](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/a8eb192a-a01a-4473-a54d-ba095c8afac7)

Click **Test step** and you will see the OUTPUT side update the Activity Status from **Done** to **In Progress**.

![Screenshot 2024-07-09 at 13 58 16](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/ecd5ab8e-1a6c-4ef9-a89b-247fcbc5a7c1)

Now let us also run the **Airtable** node, based on the new Activity Status.

![Screenshot 2024-07-09 at 14 02 07](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/adf48c3d-e71c-4b86-a8ec-bdc1efa051f9)

As you can see below the OUTPUT has been updated.

![Screenshot 2024-07-09 at 14 03 46](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/b46601d4-7a8b-4cc0-8f7a-77f5322ddd34)

Looking into the table of Airtable, to see if the existing record with Activity ID = 1 has been updated (as our intention) or a new record has been created (not intended), we see:

![Screenshot 2024-07-09 at 14 06 40](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/34299cc8-f300-4f6c-966b-243dc617f418)

The record has been successfully updated!

In addition, let us add a new Activity (here: **Commute**) with an Activity ID of **2** and an Activity Status of **Done**.

We run the **Test step** of the **Edit Fields** node:

![Screenshot 2024-07-09 at 14 13 24](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/a73d5b80-429b-4a17-8729-c9722fb09bfe)

And we run the **Test step** of the **Airtable** node:

![Screenshot 2024-07-09 at 14 15 26](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/76381985-5581-493b-8970-4166636f7d53)

And lastly, we look into the table at Airtable to see a new record for the **Commute** activity, whilst the **Lunch** activity is also still there.

![Screenshot 2024-07-09 at 14 57 19](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/9a67818f-b698-4c02-9799-390a34d2b896)

Hooray, our logic works as designed!



