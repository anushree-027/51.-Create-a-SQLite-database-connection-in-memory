# 51.-Create-a-SQLite-database-connection-in-memory
import sqlite3

try:
    conn = sqlite3.connect(':memory:')
    print("Memory database created and connected to SQLite.")

    cursor = conn.cursor()
    cursor.execute("select sqlite_version();")
    record = cursor.fetchone()

    print("SQLite Database Version is:", record)

except sqlite3.Error as error:
    print("Error while connecting to SQLite:", error)

finally:
    if conn:
        conn.close()
        print("The SQLite connection is closed.")
