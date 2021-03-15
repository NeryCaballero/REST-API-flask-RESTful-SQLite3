# Creating Tables with *sqlite3*

<hr>

```python
import sqlite3

connection = sqlite3.connect('data.db')

cursor = connection.cursor()

# MUST BE INTEGER
# This is the only place where int vs INTEGER matters—in auto-incrementing columns
create_table = "CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, username text, password text)"
cursor.execute(create_table)

create_table = "CREATE TABLE IF NOT EXISTS items (name text PRIMARY KEY, price real)"
cursor.execute(create_table)

connection.commit()

connection.close()
```

1. Import pre-built module `sqlite3`.
2. Initialize a connection via `sqlite3.connect('<name-of-file.db>')` *the file can be name as wished, with the extention db*. In here will go the URI if working with a DB.
3. Declare `cursor = connection.cursor()`.
4. Store the SQL query to Create a Table into a variable, in this case `create_table`.  `IF NOT EXISTS` checks if the table has been already created.
5. Execute the query via `cursor.execute(<pass-the-variable>)`
6. Commit, so the changes get saved.
7. Close the connection.

<hr>