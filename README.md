# Assignment 1 — NoSQL Database with MongoDB

## Description
This assignment involves working with MongoDB to perform basic database tasks such as creating a database, collections, inserting data, editing records, and running queries. The primary goal was to use the `mongo` shell to interact with the MongoDB database.

The project includes the following files and folders:
- `images/` — folder containing 16 screenshots that demonstrate the execution of each step.
- `employees.json` — JSON file containing employee data to be inserted into the `employees` collection.
- `README.md` — this file with the project description.

---

## Project Structure
```plaintext
Assignment_1_ADNoSQL/
│
├── images/                   # Folder with screenshots
│   └── Screenshots of all tasks (1 - 16)
│
├── employees.json            # JSON file with employee data
├── README.md                 # Documentation
```

---

## Step-by-Step Tasks Execution

### Task 1:
**Commands:**
1. Create a database named `hr`:
   ```javascript
   use hr
   ```
2. Check the current database:
   ```javascript
   db
   ```
3. List all collections (none exist at first):
   ```javascript
   show collections
   ```
4. Create a collection named `employees`:
   ```javascript
   db.createCollection("employees")
   ```
5. Verify that the collection has been created:
   ```javascript
   show collections
   ```

### Task 2:
**Commands:**
1. Copy the content from the `employees.json` file.
2. Insert the data into the `employees` collection:
   ```javascript
   db.employees.insertMany([...])
   ```
3. Verify the inserted data:
   ```javascript
   db.employees.find()
   ```

### Task 3:
**Commands:**
1. Delete all records from the `employees` collection:
   ```javascript
   db.employees.deleteMany({})
   ```
2. Verify that the collection is empty:
   ```javascript
   db.employees.find()
   ```

### Task 4:
**Commands:**
1. Use the terminal to import data from the `employees.json` file:
   ```bash
   mongoimport --db hr --collection employees --file employees.json --jsonArray
   ```
2. Verify that the data has been imported:
   ```javascript
   db.employees.find()
   ```

### Task 5:
**Command:**
- Find employees older than 30 years:
  ```javascript
  db.employees.find({ age: { $gt: 30 } })
  ```

### Task 6:
**Command:**
- Find employees whose age is less than or equal to 30:
  ```javascript
  db.employees.find({ age: { $lte: 30 } })
  ```

### Task 7:
**Command:**
- Find employees whose favorite food is pizza:
  ```javascript
  db.employees.find({ "favorites.food": "pizza" })
  ```

### Task 8:
**Command:**
- Update Willy's personal phone number to `"93-123-45-67"`:
  ```javascript
  db.employees.updateOne(
      { name: "Willy" },
      { $set: { "phone.personal": "93-123-45-67" } }
  )
  ```

### Task 9:
**Command:**
- Change Bob’s privileges to `"user"`:
  ```javascript
  db.employees.updateOne(
      { name: "Bob" },
      { $set: { privileges: "user" } }
  )
  ```

### Task 10:
**Command:**
- Find employees whose favorite artist is Picasso:
  ```javascript
  db.employees.find({ "favorites.artist": "Picasso" })
  ```

---

## Screenshots
The `images` folder contains 16 screenshots showcasing the execution of each step:
1. Creating the database and checking the current database.
2. Creating the `employees` collection.
3. Inserting data from `employees.json` into the collection.
4. Deleting all data.
5. Importing the data using the terminal.
6. Executing all queries for filtering, updating, and editing records.

---

## How to Push the Project to GitHub
1. Initialize a Git repository in the `Assignment_1_ADNoSQL` folder:
   ```bash
   git init
   ```
2. Add the files to the staging area:
   ```bash
   git add .
   ```
3. Commit your changes:
   ```bash
   git commit -m "Assignment 1: MongoDB tasks completed"
   ```
4. Add a remote repository:
   ```bash
   git remote add origin <URL of your repository>
   ```
5. Push the files to the GitHub repository:
   ```bash
   git push -u origin main
   ```

---

## Conclusion
The assignment has been successfully completed, and all tasks are demonstrated in the screenshots. If you have any questions, feel free to reach out!