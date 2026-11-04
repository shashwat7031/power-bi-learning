# Power Query Notes

Power Query is used to connect to data sources and prepare data before it is loaded into the Power BI model.

## Typical workflow

1. Connect to a source such as CSV, Excel, or a database.
2. Inspect column names, data types, missing values, and data quality.
3. Rename columns and remove unnecessary fields.
4. Handle nulls, duplicates, and inconsistent values.
5. Split, merge, or transform columns where needed.
6. Shape tables and combine sources when appropriate.
7. Apply changes and validate the loaded data.

## Topics to practice

- Data types and type conversion
- Replace values and fill operations
- Remove duplicates and handle nulls
- Split and merge columns
- Group By
- Merge Queries (joins)
- Append Queries
- Pivot and unpivot
- Custom columns
- Conditional columns
- Parameters
- Query folding
- Basic M language
- Refresh and data-source settings

## Good habits

- Keep transformation steps readable and named clearly.
- Validate row counts before and after important transformations.
- Avoid removing data without checking its impact.
- Prefer repeatable transformations over manual edits to source files.
