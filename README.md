Introduction

Coming from a medical background, I am used to working with patient records, but I had never worked directly with the databases that store them. This week I wrote my first SQL queries, using DBeaver and PostgreSQL. At first, the commands felt like separate pieces that I could not fit together. With practice, they started to connect, and I realized how much can be done with just a few statements: build a table, fill it, change it, and pull out exactly what you need. In this article I cover the concepts I worked with: Data Definition Language (DDL), Data Manipulation Language (DML), the WHERE clause and CASE WHEN. My examples use a small clinic database instead of a generic one.

Data Definition Language (DDL)
DDL is the part of SQL that defines the structure of a database: its tables, columns and data types. Before any patient data can be stored, there has to be a place for it to live, and CREATE TABLE builds that place.

 <img width="799" height="416" alt="image" src="https://github.com/user-attachments/assets/fa16a87f-dc29-474a-b149-289b65dd6c5a" />


This creates a patients table where each patient gets a unique ID, similar to a file number in a clinic.

Data Manipulation Language (DML)
Where DDL builds the structure, DML works with the data inside it. The three commands I used most were INSERT, UPDATE and DELETE.
INSERT adds new records:

<img width="783" height="541" alt="image" src="https://github.com/user-attachments/assets/fe519c0c-4d33-4c2a-8499-5b41ecfac0da" />

 UPDATE changes existing records, and DELETE removes them. Both need a condition; otherwise, they affect every row in the table, which is a mistake worth avoiding early.

<img width="799" height="304" alt="image" src="https://github.com/user-attachments/assets/04099038-2fb2-4725-b107-1b8ef1975f61" />
 
The WHERE Clause
WHERE filters rows so that only those meeting a condition are returned. Instead of scanning a whole table, you ask a specific question, much like searching a register for one clinic's patients.

 <img width="800" height="450" alt="image" src="https://github.com/user-attachments/assets/e28aa6c8-6882-46dc-8a29-3c9d7d1aecf5" />

The = operator finds exact matches, > finds values above a threshold, and BETWEEN selects a range.

CASE WHEN
CASE WHEN applies conditions and returns different results depending on which one is met. It works like clinical triage rules: if the patient meets this criterion, assign this category.

 <img width="800" height="300" alt="image" src="https://github.com/user-attachments/assets/4c7c6d9c-12c5-480c-a229-a3c93a3547fb" />

This was the hardest concept for me. However, it helped me to read each WHEN line as an if statement and to notice that SQL checks them from top to bottom and stops at the first match.
Once that clicked, I saw how useful it is for grouping data into meaningful categories.

