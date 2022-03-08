
# 1- Explain what is indexing in simple analogy?

**Answer-** In general, indexing refers to the organization of data according to a specific schema or plan. In IT, the term has various similar uses including, among other things, making information more presentable and accessible.

**or**

Indexing is a data structure technique which allows you to quickly retrieve records from a database file. An Index is a small table having only two columns. The first column comprises a copy of the primary or candidate key of a table.


# 2- why do we use it?

**Answer-** Indexes are used to quickly locate data without having to search every row in a database table every time a database table is accessed. Indexes can be created using one or more columns of a database table, providing the basis for both rapid random lookups and efficient access of ordered records.

Or

**Answer:**
An index is a schema object that contains an entry for each value that appears in the indexed column(s) of the table or cluster and provides direct, fast access to rows.
Indexes allow the database application to find data fast; without reading the whole table

The users cannot see the indexes, they are just used to speed up searches/queries.

**Note:** Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So you should only create indexes on columns (and tables) that will be frequently searched against.

**Syntax:**
CREATE INDEX index_name
ON table_name (column_name)

**Note:** The syntax for creating indexes varies amongst different databases. Therefore: Check the syntax for creating indexes in your database.

**Example:**
CREATE INDEX IXuser_lilink_item_id ON user_line_item_link (line_item_id);


# 3- Explain in simple terms how indexing pros and cons.

**Answer-**

**Indexing Advantages:**
 - Speed up SELECT queries and reports
 - Reduce I/O and Lowest I/O
 - Fast Data Access
 - Prevent duplication (primary,unique) **or** Helps to make a row unique or without duplicates(primary,unique) 
 - If index is set to fill-text index, then we can search against large string values. for example to find a word from a sentence etc.
 

**Indexing Disadvantages:**
 - Since Indexes physically take up space on the Disk, using the Index will increase the extra disk cost unless necessary.
 - In general, indexes improve performance in our Select queries and slow down DML (insert, update, delete) operations. Especially in tables where too many DML operations are performed, index should not be used.
 - When we use index, database has an extra load because the maintenance (index maintenance) load of the database will increase.



 # 4- If you can explain a bit about the data structure used.

 **Answer-** B-trees

B-trees are the most commonly used data structures for indexes as they are time-efficient for lookups, deletions, and insertions. All these operations can be done in logarithmic time. Data that is stored inside of a B-tree can be sorted. Indexes that use hash tables are generally referred to as hash index.


# 5- what is compound indexing?

**Answer-** compound indexes are those indexes where a single index field contains references to multiple fields. In MongoDB, the compound index can contain a single hashed index field, if a field contains more than one hashed index field then MongoDB will give an error