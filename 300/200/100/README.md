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

MORE
