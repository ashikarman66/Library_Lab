# 📚 Library Management Database (SQL Lab)

## 📌 Project Title
Design and Implementation of Library Management Database Using SQL Constraints and ALTER Operations

---

## 🎯 Objectives

- Create a relational database using MySQL  
- Implement Primary Key, Foreign Key, Unique, and Check constraints  
- Use ENUM and DEFAULT values  
- Test constraint violations  
- Perform ALTER operations (ADD, MODIFY, DROP, RENAME)  
- Understand referential integrity in relational databases  

---

## 🗄️ Database Name

`library_lab`

---

## 🏗️ Tables Created

### 1️⃣ MEMBER
- **MemberID** → Primary Key  
- **FullName** → NOT NULL  
- **Email** → NOT NULL, UNIQUE  
- **Age** → CHECK (Age ≥ 12)  
- **Gender** → ENUM ('MALE', 'FEMALE', 'OTHER') *(later dropped)*  
- **Phone** → Added later using ALTER  

---

### 2️⃣ BOOK
- **BookID** → Primary Key  
- **Title** → NOT NULL  
- **ISBN** → NOT NULL, UNIQUE  
- **Price** → CHECK (Price ≥ 0)  
- **Status** → ENUM with DEFAULT 'AVAILABLE'  
- **Availability** → Renamed from Status  

---

### 3️⃣ LOAN (Renamed to BORROW)
- **LoanID** → Primary Key  
- **MemberID** → Foreign Key → MEMBER(MemberID)  
- **BookID** → Foreign Key → BOOK(BookID)  

---

## 🔗 Relationships

- One MEMBER can borrow multiple BOOKS  
- LOAN/BORROW table connects MEMBER and BOOK  
- Foreign Keys maintain referential integrity  

---

## 🧪 Constraint Testing

The following errors were tested:

- ❌ Duplicate Email → UNIQUE constraint violation  
- ❌ Invalid MemberID in LOAN → Foreign Key constraint violation  
- ❌ Negative Price → CHECK constraint violation  

All constraints worked correctly.

---

## 🔄 ALTER Operations Performed

- Added `Phone` column in MEMBER  
- Modified BOOK `Price` datatype  
- Renamed `Status` → `Availability`  
- Dropped `Gender` column  
- Added named CHECK constraint on `Phone`  
- Renamed `LOAN` table → `BORROW`  

---

## 📊 Key Concepts Demonstrated

- Relational Database Design  
- Primary Key & Foreign Key  
- Unique & Check Constraints  
- ENUM and DEFAULT values  
- Data Integrity Enforcement  
- Table Modification using ALTER  

---

## ✅ Conclusion

This project demonstrates the successful design and implementation of a relational database using MySQL. It verifies how constraints enforce data integrity and shows how database structures can be modified dynamically using ALTER statements. The experiment strengthens practical knowledge of SQL and relational database management systems.
