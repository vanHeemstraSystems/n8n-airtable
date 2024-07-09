# 100 - Create a workflow in n8n

Create a new workflow **Activity Data Management** and add a **Edit Fields** node to it. We'll need the **Edit Fields** node to make sure that we send well-formatted data to the **Airtable** node.

![Screenshot 2024-07-09 at 10 25 13](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/c33c96d9-70ed-45e1-a872-58eb4e44a708)

Open the **Edit Fields** node and add three values of ```String type```. For each of these three values, do the following.

- In the **Activity ID** field, enter the same name of the column in the **Airtable** table (here: ```Activity ID```). In the **Value** field, enter a unique number (e.g. **1**).
- In the **Activity Name** field, enter the same name of the column in the **Airtable** table (here: ```Activity Name```). In the **Value** field, enter an activity name (e.g. **Lunch**).
- In the **Activity Status** field, enter the same name of the column in the **Airtable** table (here: ```Activity Status```). In the **Value** field, enter an activity status (e.g. **Not Started**).

![Screenshot 2024-07-09 at 10 29 27](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/cd5ecc53-be1d-4b3f-b60c-b1ede8ba9b5f)

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

![Screenshot 2024-07-09 at 12 03 00](https://github.com/vanHeemstraSystems/n8n-airtable/assets/1499433/edebb100-23f2-43c8-9401-8d04ae16f049)


 
MORE
