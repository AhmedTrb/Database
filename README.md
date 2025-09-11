# Simple SQLite-Like Database in C

### Overview

This project is a simple SQLite-inspired database implemented in C, designed to demonstrate core 
database concepts:
- Persistent storage of rows in leaf nodes using a B+ tree.
- Efficient search, insert, and traversal operations.
- Basic command parsing for inserting and selecting rows.

The primary goal of this project is learning by doing: to deeply understand how databases internally manage data, optimize read/write operations, and scale efficiently.

---
## Motivation
My journey into databases started with a simple video about indexing, which sparked my curiosity about how databases store data, manage queries, and optimize performance. Reading about database internals — pages on disk, I/O costs, and tree-based indexing

I wanted to go beyond theory and experience the challenges firsthand, so I decided to build a minimal database engine to better understand and visualize these concepts.

I detailed my learning about Databases basic data storage and why using B+trees in this Notion page [Databases](https://www.notion.so/Databases-2686bf1d695080078f87f768de334481?source=copy_link)

---
## Features 

This simple database supports one table with the following schema:
- `id` (integer)
- `username` (string, max 32 characters)
- `email` (string, max 255 characters)

The database supports the following commands:
- `insert <id> <username> <email>`: Inserts a new row into the database.
- `select`: Retrieves and displays all rows in the database.
- `bulk_insert` inserts 1000 rows with random data for testing purposes.

Meta commands:
- `.exit`: Exits the database program and frees allocated memory.
- `.btree`: Displays the structure of the B+ tree.
- `.constants`: Displays constants used in the database.

---
## Building and Running
To build and run the database, follow these steps:
1. Clone the repository:
   ```bash
   git clone https://github.com/AhmedTrb/Database.git
   cd Database
    ```
2. Compile the code using `gcc` and run the executable:
   ```bash
   gcc -o db db.c
   ./db database.db
   ```
---
## Acknowledgment 
This project follows this excellent step-by-step tutorial [DB Tutorial](https://cstack.github.io/db_tutorial), which guided the initial implementation of:
- B+ tree structure for table storage.
- Row storage in leaf nodes.
- Disk persistence through simple file-based storage.

I built upon this foundation by adding new utilities and experimenting with different aspects of the database to understand each component in depth.