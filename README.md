# Library Management System

A simple **Library Management System** built with **Python** and **MySQL** that allows you to:

- **INSERT** new books into the catalog  
- **UPDATE** existing book records  
- **DELETE** books from the catalog  
- **DISPLAY** all books in the catalog  
- **SEARCH** for books by title, author, or ISBN  

---

## Features

1. **INSERT**  
   - Add new books with details: Title, Author, ISBN, Publisher, Year, Quantity.  
2. **UPDATE**  
   - Modify any field of an existing book record.  
3. **DELETE**  
   - Remove books by their unique ID or ISBN.  
4. **DISPLAY**  
   - List all books in a clean tabular format.  
5. **SEARCH**  
   - Find books by Title, Author, or ISBN (supports partial matches).  

---

## Prerequisites

- Python 3.7+  
- MySQL Server 5.7+  
- `mysql-connector-python` (or `PyMySQL`)  

---

## Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/library-management-system.git
   cd library-management-system
   ```

2. **Create & activate a virtual environment (optional but recommended)**  
   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Install Python dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

---

## Database Setup

1. **Start MySQL** and log in as root (or a user with CREATE privileges):  
   ```sql
   mysql -u root -p
   ```

2. **Create a new database**:  
   ```sql
   CREATE DATABASE library_db;
   USE library_db;
   ```

3. **Create the `books` table** (run the SQL in `schema.sql`):  
   ```sql
   -- schema.sql
   CREATE TABLE books (
     id INT AUTO_INCREMENT PRIMARY KEY,
     title VARCHAR(255) NOT NULL,
     author VARCHAR(255) NOT NULL,
     isbn VARCHAR(20) UNIQUE NOT NULL,
     publisher VARCHAR(255),
     year YEAR,
     quantity INT DEFAULT 1
   );
   ```

---

## Configuration

1. **Copy the sample config** and update with your MySQL credentials:  
   ```bash
   cp config_example.py config.py
   ```
2. **Edit** `config.py`:
   ```python
   DB_CONFIG = {
       'host': 'localhost',
       'user': 'your_mysql_username',
       'password': 'your_mysql_password',
       'database': 'library_db'
   }
   ```

---

## Usage

Run the main script to launch the interactive menu:

```bash
python pro12bSECRET.py
```

You will see options:

```
1. Insert 
2. Update 
3. Delete 
4. Display 
5. Search 
6. Exit
```

- **Insert**: Enter book details when prompted.  
- **Update**: Provide the Book ID or ISBN, then choose which field(s) to update.  
- **Delete**: Provide the Book ID or ISBN to remove the record.  
- **Display**: Shows all books in a formatted table.  
- **Search**: Enter a keyword to search by Title, Author, or ISBN.

---

