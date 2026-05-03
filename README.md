Launch an RDS instance and connect to it using a database client.
 1: Amazon RDS Setup

Configuration Details

DB Instance Identifier: mary-rds-db

DB Instance Class: db.t4g.micro

Engine: MySQL

Username :admin

Password: Mmesoma1234

Storage: Default (20GB)

Public Access: Enabled

Steps Taken

1. Navigated to RDS in AWS Console
2. Clicked Create Database
3. Selected MySQL and Free Tier template
4. Entered database credentials and instance name
5. Enabled public access
6. Configured security group to allow port 3306
7. Created the database and waited until status showed Available

 2: Connecting via AWS CloudShell

 Steps

1. Opened CloudShell from AWS Console
3. Connected to the RDS instance:
mysql -h mary-rds-db.cb2gyoci6nx7.eu-central-1.rds.amazonaws.com -P 3306 --ssl-ca /certs/global-bundle.pem --ssl-verify-server-cert -u admin -p

4. Entered password: Mmesoma1234
5. Successfully accessed the MySQL database

3: SQL CRUD Operations

CREATE DATABASE school;
USE school;

CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    age INT
);

Insert Data (CREATE)

INSERT INTO students (name, age)
VALUES ('Mary', 24),
       ('Femi', 26);

Read Data

SELECT * FROM students;

Update Data

UPDATE students
SET age = 23
WHERE name = 'Mary';

Delete Data

DELETE FROM students
WHERE name = 'Femi';

Read Data

SELECT * FROM students;


4: DynamoDB Setup

Service Used

Amazon DynamoDB

Table Configuration

Table Name:mary-users
Primary Key:userid (String)

steps
1. Opened DynamoDB in AWS Console
2. Clicked Create Table
3. Entered table name and partition key
4. Created the table

5: DynamoDB Operations

Insert Item

json
{
  "userid": {"S": "1"},
  "name": {"S": "Alice"},
  "age": {"N": "25"}
}

recreated for Femi, Isiah and Alice

Retrieve Item

Used Explore Items
Queried using userid = 1

Update Item

Updated age from 25 → 26

 Delete Item

Deleted the item from the table
<img width="1325" height="656" alt="dynamo setup" src="https://github.com/user-attachments/assets/299dd345-2597-468b-a502-9f714e47a837" />
<img width="1323" height="656" alt="Database2" src="https://github.com/user-attachments/assets/dc35fe57-fbd6-4822-ae20-8f72baf3a76a" />
<img width="1326" height="656" alt="Database1" src="https://github.com/user-attachments/assets/f697dbb1-a03c-44f4-bbe2-f5d5595d0a79" />
<img width="1330" height="661" alt="rds database" src="https://github.com/user-attachments/assets/3b7756e8-cc06-4c3e-a6d6-31f578160ac8" />
<img width="1326" height="654" alt="connection to database" src="https://github.com/user-attachments/assets/f6998f62-55b3-409b-8780-a0c13aa62a39" />
