
## Summary Table: All Breaks Fixed

| Break | Broken Query | Fix |
|-------|--------------|-----|
| **A** | `SELECT AVG(price) FROM trades GROUP BY ticker WHERE price > 100;` | `SELECT AVG(price) FROM trades WHERE price > 100 GROUP BY ticker;` |
| **B** | `SELECT ticker, SUM(quantity) FROM trades GROUP BY trade_date;` | `SELECT ticker, SUM(quantity) FROM trades GROUP BY ticker;` |
| **C** | `SELECT COUNT(*) FROM trades WHERE ticker = 'aapl';` | `SELECT COUNT(*) FROM trades WHERE ticker = 'AAPL';` |
| **D** | `INSERT INTO trades (trade_date, price, quantity, broker) VALUES (...);` | Add `ticker` to the column list and values |


| Break | Your Answer | Correct? |
|-------|-------------|----------|
| **A** | Move `WHERE` before `GROUP BY` | ✅ Correct |
| **B** | Remove `trade_date` from `GROUP BY` (or add `ticker` to `GROUP BY`) | ✅ Correct |
| **C** | Use uppercase `'AAPL'` (or `UPPER(ticker)`) | ✅ Correct |
| **D** | Include `ticker` in `INSERT` | ✅ Correct |

---

---

### Question 1: GROUP BY order (ticker, trade_date vs trade_date, ticker)

| Your answer | Correct? | Notes |
|-------------|----------|-------|
| `ticker, trade_date` prioritises arranging ticker from A‑Z; `trade_date, ticker` prioritises arranging trade_date from early to end | ✅ **Correct** | The order in `GROUP BY` affects the **default sorting** in some databases, but the **aggregation result** (sums/counts) is identical. For composite keys, the order matters for indexing and performance. |

---

### Question 2: WHERE vs HAVING

| Your answer | Correct? | Notes |
|-------------|----------|-------|
| `WHERE` filters rows **before grouping**; `HAVING` filters groups **after grouping** | ✅ **Correct** | |
| `WHERE price > 100` is wrong when you need to filter on an **aggregate** (e.g., `AVG(price) > 100`) | ✅ **Correct** | `HAVING AVG(price) > 100` is wrong when you need to filter on **individual rows** before grouping | ✅ **Correct** |

---

### Question 3: DROP TABLE IF EXISTS

| Your answer | Correct? | Notes |
|-------------|----------|-------|
| Deletes the table only if it exists; prevents errors in automated scripts when the table doesn't exist | ✅ **Correct** | Without `IF EXISTS`, `DROP TABLE` throws an error if the table is missing – this can break a script. |

---

### Question 4: Why LOWER(broker) in GROUP BY

| Your answer | Correct? | Notes |
|-------------|----------|-------|
| Without `LOWER()`, `'Goldman'` and `'goldman'` would be treated as **different groups** | ✅ **Correct** | |
| Real‑world data has case inconsistencies; you must normalise (lower/upper) for correct grouping | ✅ **Correct** | This teaches you to **clean data** before aggregating |

---
