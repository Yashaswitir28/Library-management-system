# Library-management-system
# Library Management System (LMS)

## Overview
This project is a Library Management System designed to efficiently handle book records, members, staff, transactions, and more. The system is implemented using SQL and follows a structured relational database schema to support essential library operations.

## Features
- **Book Management**: Maintain records of books, authors, publishers, and categories.
- **Member Management**: Store details of library members and their borrowing history.
- **Staff Management**: Track library staff responsible for managing operations.
- **Transactions**: Handle book lending and returns with due date tracking.
- **Fine System**: Automatically calculate fines for overdue books.
- **Book Requests**: Allow members to request books not currently available.

## Database Schema
The database consists of the following tables:

### 1. **Books**
Stores book-related information.
```
book_id (Primary Key, Auto Increment)
title
category_id (Foreign Key -> Categories)
author_id (Foreign Key -> Authors)
publisher_id (Foreign Key -> Publishers)
publication_year
isbn
quantity_available
```

### 2. **Authors**
Stores author details.
```
author_id (Primary Key, Auto Increment)
author_name
```

### 3. **Categories**
Stores book categories.
```
category_id (Primary Key, Auto Increment)
category_name
```

### 4. **Publishers**
Stores publisher details.
```
publisher_id (Primary Key, Auto Increment)
publisher_name
```

### 5. **Members**
Stores library members.
```
member_id (Primary Key, Auto Increment)
name
email
phone
address
membership_date
```

### 6. **Staff**
Stores library staff details.
```
staff_id (Primary Key, Auto Increment)
name
email
phone
position
hire_date
```

### 7. **Transactions**
Stores book issue and return records.
```
transaction_id (Primary Key, Auto Increment)
book_id (Foreign Key -> Books)
member_id (Foreign Key -> Members)
issue_date
return_date
status (Issued/Returned)
```

### 8. **Fines**
Stores overdue fine records.
```
fine_id (Primary Key, Auto Increment)
transaction_id (Foreign Key -> Transactions)
fine_amount
payment_status (Paid/Pending)
```

### 9. **Book Requests**
Stores member book requests.
```
request_id (Primary Key, Auto Increment)
member_id (Foreign Key -> Members)
book_title
request_date
status (Pending/Approved/Rejected)
```

## SQL Scripts
The project includes:
- Schema creation scripts (`schema.sql`)
- Sample data insertion scripts (`data.sql`)
- Query scripts for reports (`queries.sql`)

## Installation & Setup
1. Install MySQL/PostgreSQL.
2. Create a new database:
   ```sql
   CREATE DATABASE library_management;
   ```
3. Run the schema script:
   ```sql
   SOURCE schema.sql;
   ```
4. Insert sample data:
   ```sql
   SOURCE data.sql;
   ```

## Usage
- Run queries in `queries.sql` to generate reports.
- Modify schema as needed for additional functionalities.

## Future Enhancements
- Implement a web-based interface.
- Add user authentication and role-based access control.
- Integrate an automated notification system.

## License
This project is open-source and available under the MIT License.

## Contributors
Feel free to contribute by submitting issues or pull requests!

---


