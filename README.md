# SQL-Practice
Data table learning 1.0 (ˉ﹃ˉ)

# 🗄️ SQL Command Reference

Quick lookup table for the SQL commands you used.

---

## 📌 Table Management

| Command | What it does |
|---------|--------------|
| `DROP TABLE IF EXISTS (name)` | Delete the whole table if it exists (no error if missing) |
| `CREATE TABLE (name) (\n  {column}  (Data type) \n)` | Create a new empty table |
| `Continue with comma (,) except the last` | Continue code writing |
| `After ) write ;` | End code writing |

### Data Types

| Type | Meaning |
|------|---------|
| `INTEGER` | Whole number |
| `TEXT` | String (text) |
| `REAL` | Decimal number |
| `PRIMARY KEY` | Unique row identifier (only one per table) |

---

## 📥 Data Insertion

| Command | What it does |
|---------|--------------|
| `INSERT INTO (name) ({columns,}) VALUES \n ({datas})` | Add rows of data |
| `For text need to put '__'` | Turns text into str |

---

## 🔍 Querying (SELECT)

| Clause / Function | Purpose |
|-------------------|---------|
| `SELECT {column}` | Choose which columns to show (variables) |
| `AS {new_column_name}` | Rename a column in the output (result) |
| `FROM (name)` | Which table to read |
| `WHERE {}` | Filter rows before grouping |
| `GROUP BY {}` | Combine rows into groups (one per unique value) |
| `ORDER BY {},` | Sort the final result (`ASC` = ascending, `DESC` = descending) |

### Aggregate Functions (used with `GROUP BY`)

| Function | What it calculates |
|----------|--------------------|
| `AVG{column}` | Average of the column values |
| `SUM{column}` | Sum of the column values |
| `COUNT{column}` | Number of non‑null rows |

---

## 📋 SQL Execution Order (Conceptual)

| Step | Operation |
|:----:|-----------|
| 1 | `FROM` → which table |
| 2 | `WHERE` → filter rows |
| 3 | `GROUP BY` → create groups |
| 4 | `SELECT` → pick columns + aggregates |
| 5 | `ORDER BY` → sort results |

---

## ✅ Quick Command Cheat Sheet

| Action | SQL Keyword |
|--------|-------------|
| Delete a table | `DROP TABLE IF EXISTS` |
| Create a table | `CREATE TABLE` |
| Add rows | `INSERT INTO` |
| Show data | `SELECT` |
| Filter rows | `WHERE` |
| Group rows | `GROUP BY` |
| Sort results | `ORDER BY` |
| Rename output column | `AS` |
| Calculate average | `AVG()` |
| Calculate sum | `SUM()` |
| Count rows | `COUNT()` |
