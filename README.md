# Exp 7 CRUD Operations on Products Collection using MongoDB

**Date:01/09/2026**

## AIM:

To implement **CRUD (Create, Read, Update, and Delete) Operations using MongoDB** on a Products collection to store, retrieve, modify, and delete product information.

## DESIGN STEPS:

### Step 1:

Fork the given repository and clone the forked repository from GitHub.

### Step 2:

Open **MongoDB Shell (mongosh)** or MongoDB Compass and create a database for storing product information.

### Step 3:

Create a collection named **Products** with the fields **id, name, brand, price, category, stock,** and **tags**.

### Step 4:

Insert the following product records into the Products collection.

| id | name       | brand    | price | category    | stock | tags                       |
| -- | ---------- | -------- | ----: | ----------- | ----: | -------------------------- |
| 1  | Laptop     | Dell     | 55000 | Electronics |    30 | ["computer", "technology"] |
| 2  | Smartphone | Samsung  | 30000 | Electronics |    50 | ["mobile", "android"]      |
| 3  | Headphones | Sony     |  2500 | Accessories |   100 | ["audio", "music"]         |
| 4  | Smartwatch | Apple    | 45000 | Electronics |    20 | ["wearable", "ios"]        |
| 5  | Keyboard   | Logitech |  1200 | Accessories |    80 | ["computer", "typing"]     |

### Step 5:

Perform the **Create operation** by inserting all the given product documents into the Products collection.

### Step 6:

Perform the **Read operation** to display all the documents available in the Products collection.

### Step 7:

Retrieve products based on conditions such as **product ID, category, price, brand, stock,** and **tags**.

### Step 8:

Perform the **Update operation** to modify selected product information such as **price, stock,** or **tags**.

### Step 9:

Perform an update operation on multiple documents belonging to a particular product category.

### Step 10:

Perform the **Delete operation** to remove a selected product document from the Products collection.

### Step 11:

Display the final Products collection and verify the changes made through the CRUD operations.

### Step 12:

Execute all the MongoDB commands, capture the required outputs, commit the completed experiment, and push the changes to the forked GitHub repository.


## PROGRAM:

To create a database
```
use mydb
```

To create collection "product"
```
db.createCollection("products")
```

To insert all documents in product collections
```
`db.products.insertMany([
    {
      _id: 1,
      name: "Laptop",
      brand: "Dell",
      price: 55000,
      category: "Electronics",
      stock: 30,
      tags: ["computer", "technology"]
    },
    {
      _id: 2,
      name: "Smartphone",
      brand: "Samsung",
      price: 30000,
      category: "Electronics",
      stock: 50,
      tags: ["mobile", "android"]
    },
    {
      _id: 3,
      name: "Headphones",
      brand: "Sony",
      price: 2500,
      category: "Accessories",
      stock: 100,
      tags: ["audio", "music"]
    },
    {
      _id: 4,
      name: "Smartwatch",
      brand: "Apple",
      price: 45000,
      category: "Electronics",
      stock: 20,
      tags: ["wearable", "ios"]
    },
    {
      _id: 5,
      name: "Keyboard",
      brand: "Logitech",
      price: 1200,
      category: "Accessories",
      stock: 80,
      tags: ["computer", "typing"]
    }
  ])
```

To read all documents in product collections
```
db.products.find().pretty()
```

To read products below 5000
```
db.products.find({ price: { $lt: 5000 } })
```

To read only accessories
```
db.products.find({ category: "Accessories" })

```

To read electronics below 50,000
```
db.products.find({
  $and: [
    { category: "Electronics" },
    { price: { $lt: 50000 } }
  ]
})
```

To update laptop price
```
db.products.updateOne(
  { name: "Laptop" },
  { $set: { price: 52000 } }
)
```

To increase keyboard stock by 10
```
db.products.updateOne(
  { name: "Keyboard" },
  { $inc: { stock: 10 } }
)
```

To add premium tag to smartwatch
```
db.products.updateOne(
  { name: "Smartwatch" },
  { $push: { tags: "premium" } }
)
```

To delete Keyboard
```
db.products.deleteOne({
  name: "Keyboard"
})

```

## OUTPUT:
After Insertions
<img width="819" height="94" alt="image" src="https://github.com/user-attachments/assets/f2080e4c-79d4-4ee2-915a-ba3d507cb604" />

After read operation
<img width="601" height="806" alt="image" src="https://github.com/user-attachments/assets/a76c3589-34b6-4eda-b3fc-e7f00e449a2c" />


To read products below 5000
<img width="839" height="483" alt="image" src="https://github.com/user-attachments/assets/a7199b83-724f-4b72-9e10-1829cf7c245f" />


To read only accessories
<img width="840" height="485" alt="image" src="https://github.com/user-attachments/assets/57f983b2-b1ad-4f1a-93bd-2f095c6733c5" />

To read electronics below 50,000
<img width="828" height="466" alt="image" src="https://github.com/user-attachments/assets/a221790c-62b0-4654-a633-71b85acad5db" />


After updating the product collections

<img width="630" height="800" alt="image" src="https://github.com/user-attachments/assets/988cb312-02ca-4ed7-94f3-28a9c9f05754" />

After delete operation in product collection

<img width="633" height="648" alt="image" src="https://github.com/user-attachments/assets/4d9fdd53-0fe8-4368-ac3f-f074755b8612" />

## RESULT:

The **CRUD Operations on the Products Collection using MongoDB** were implemented successfully. The product documents were created, retrieved, updated, and deleted using appropriate MongoDB commands, and the final changes were successfully verified in the Products collection.



