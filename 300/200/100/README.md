# 100 - Create a workflow in n8n

Create a new workflow **Activity Data Management** and add  a **Set** node to it. We'll need the **Set** node to make sure that we send well-formatted data to the **Airtable** node.

Open the **Set** node and add three values of ```String type```. For each of these three values, do the following.

- In the **Activity ID** field, enter the same name of the column in the **Airtable** table (here: ```Activity ID```). Toggle the **Keep Only Set** button to ```true``` (green). In the **Value** field, enter a unique number (e.g. **1**).
- In the **Activity Name** field, enter the same name of the column in the **Airtable** table (here: ```Activity Name```).  Toggle the **Keep Only Set** button to ```true``` (green). In the **Value** field, enter an activity name (e.g. **Lunch**).
- In the **Activity Status** field, enter the same name of the column in the **Airtable** table (here: ```Activity Status```).  Toggle the **Keep Only Set** button to ```true``` (green). In the **Value** field, enter an activity status (e.g. **Done**).



MORE
