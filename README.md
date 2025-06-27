
# 📘 Task 3 – Writing Basic SELECT Queries

## 🎯 Objective
This task focuses on writing **basic SQL queries** to extract and analyze data from the Library Management database.  
It demonstrates concepts like projection, filtering, sorting, joining, and aggregation.

---

## 🛠 Tools Used
- **MySQL Workbench**
- **DB Browser for SQLite** (optional)

---

##  Files Included
- `Library-DB-Schema-1.sql` – SQL script containing Queries Like Insert , Delete And Update
- `Library-DB-Schema-1.sql` – SQL script To Make The Schema
- `task3.sql` – SQL script containing all 11 SELECT queries
- `README.md` – This documentation


---

## 📋 Queries Overview

### 1. View all authors
```sql
SELECT * FROM author;
```

### 2. Count total number of books
```sql
SELECT COUNT(BookID) FROM book;
```

### 3. Get author name and book title
```sql
SELECT Name, Title 
FROM author, book 
WHERE author.AuthorID = book.AuthorID;
```

### 4. Number of books in each category
```sql
SELECT CategoryID, COUNT(*) AS total_Books 
FROM book 
GROUP BY CategoryID;
```

### 5. Count of distinct staff names
```sql
SELECT DISTINCT COUNT(Name) FROM staff;
```

### 6. Show MemberID and LoanDate using RIGHT JOIN
```sql
SELECT member.MemberID, loan.LoanDate 
FROM member 
RIGHT JOIN loan ON member.MemberID = loan.MemberID;
```

### 7. Find books with "Secret" in title
```sql
SELECT * 
FROM loan, book 
WHERE Title LIKE "%Secret%";
```

### 8. Retrieve loans between May and July 2025 ordered by LoanDate
```sql
SELECT * 
FROM loan 
WHERE LoanDate BETWEEN "2025-05-01" AND "2025-07-01" 
ORDER BY LoanDate ASC;
```

### 9. Count of members who borrowed each book title
```sql
SELECT Title, COUNT(MemberID) AS total_ID 
FROM book 
LEFT JOIN loan ON book.BookID = loan.BookID 
GROUP BY Title 
ORDER BY Title ASC;
```

### 10. Staff names and IDs with CategoryID between 1 and 5
```sql
SELECT staff.Name, staff.StaffID 
FROM staff, category 
WHERE category.CategoryID BETWEEN 1 AND 5;
```

### 11. BookIDs for loans between Jan and May 2025
```sql
SELECT BookID 
FROM loan 
WHERE LoanDate >= "2025-01-01" AND LoanDate <= "2025-05-30" 
ORDER BY MemberID DESC;
```

---

##  Author

**Aarya Gupta**  
