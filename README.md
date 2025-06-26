# Library-DB-3
# 📘 Task 3 – Basic SQL SELECT Queries

## 🎯 Objective:
The goal of this task is to demonstrate the ability to retrieve and filter data using SQL. This includes mastering:
- `SELECT`, `WHERE`, `ORDER BY`, `LIKE`, `BETWEEN`, `GROUP BY`, `JOIN`, `DISTINCT`, and `LIMIT`,`Right Join`, `Left Join` .

---

## 🛠 Tools Used:
- **MySQL Workbench**
- **DB Browser for SQLite (optional)**

---

## 📋 Queries Included:

### 1. View all data from the author table
`Select`
----> `SELECT` * FROM author;

###2. Count total number of books
---> SELECT `COUNT(BookID)` FROM book;


### 3. Display Author Name and Book Title
---> `SELECT` Name, Title 
     `FROM` author, book 
     `WHERE` author.AuthorID = book.AuthorID;


## 4. Number of books in each category
----> SELECT CategoryID, `COUNT(*)` `AS` total_Books
      FROM book 
      `GROUP BY` CategoryID;

## 5.  Count of distinct staff names
---> SELECT `DISTINCT` COUNT(Name) FROM staff;

## 6. Show MemberID and LoanDate using RIGHT JOIN
---> SELECT member.MemberID, loan.LoanDate 
     FROM member 
     `RIGHT JOIN` loan `ON` member.MemberID = loan.MemberID;

# 7. Search for books with "Secret" in the title

---> SELECT * 
     FROM loan, book 
     WHERE Title `LIKE` "%Secret%";


## 8. Retrieve loans between two dates, sorted by LoanDate
---> SELECT * 
     FROM loan 
     WHERE LoanDate `BETWEEN` "2025-05-01" AND "2025-07-01" 
     ORDER BY LoanDate ASC;

## 9. Count of loans per book title 
  --> SELECT Title, COUNT(MemberID) AS total_ID 
      FROM book 
      `LEFT JOIN` loan ON book.BookID = loan.BookID 
      GROUP BY Title 
      ORDER BY Title ASC;

      
## 10. Select staff names with CategoryID 'between' 1 and 5
---> SELECT staff.Name, staff.StaffID 
    FROM staff, category 
    WHERE category.CategoryID `BETWEEN` 1 AND 5;


    
## 11. Get BookIDs from loans between date range
----> SELECT BookID 
      FROM loan 
      WHERE LoanDate >= "2025-01-01" `AND` LoanDate <= "2025-05-30" 
      ORDER BY MemberID DESC;

