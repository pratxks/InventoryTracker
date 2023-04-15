# InventoryTracker

This app is a management tool for businesses that need to track their inventory levels and job work progress. Users can create multiple organizations within the app, and for each organization, they can create a list of products and set their stock quantity. Users can then create job works, which represent projects or tasks that require the use of one or more products from the inventory. For each job work, the user can select the products used and their quantity used. The app stores the job work creation date and completion date in the database, as well as every product used with its corresponding date when it was used.

The app allows users to track inventory levels in real-time, and it provides insight into how much of each product is being used in different job works. This can help businesses make informed decisions about when to restock products and how much inventory they need to keep on hand to meet their project needs. With this app, users can streamline their inventory management and job work tracking processes, saving time and increasing efficiency.

## Database Structure

**1. Organizations table:**

    id (integer, primary key)
    name (string)

**2. Products table:**

    id (integer, primary key)
    name (string)

 **3. Inventories table:**

    id (integer, primary key)
    organization_id (integer, foreign key to Organizations table)
    product_id (integer, foreign key to Products table)
    quantity (integer)

**4. JobWorks table:**

    id (integer, primary key)
    organization_id (integer, foreign key to Organizations table)
    name (string)
    creation_date (datetime)
    completion_date (datetime)

**5. JobWorkEntries table:**

    id (integer, primary key)
    job_work_id (integer, foreign key to JobWorks table)
    product_id (integer, foreign key to Products table)
    quantity (integer)
    entry_date (datetime)
