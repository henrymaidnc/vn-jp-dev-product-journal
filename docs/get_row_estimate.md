# Export Table Names and Record Counts (PostgreSQL)

To quickly list all tables in the `public` schema along with their record counts, you can use PostgreSQL’s internal statistics:

```sql
SELECT relname AS table_name,
       reltuples::bigint AS estimated_records
FROM pg_class
WHERE relkind = 'r'
  AND relnamespace = 'public'::regnamespace
ORDER BY estimated_records DESC;

## 📌 Notes

- `reltuples` gives **estimated row counts** (fast, good for overview).  
- For **exact counts**, use `COUNT(*)` per table — but this can be slow on large datasets.  
- In DBeaver, you can right‑click the result grid → **Export Data** → save as CSV/Excel.  
