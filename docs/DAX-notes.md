# DAX Notes

A practical notebook for DAX patterns used while building Power BI reports.

## Measures vs. calculated columns

- **Measure:** evaluated in the current filter context; commonly used in visuals and aggregations.
- **Calculated column:** evaluated row by row during model refresh and stored in the model.

## Common aggregation functions

| Function | Use |
|---|---|
| `SUM()` | Add values from one column |
| `COUNTROWS()` | Count rows in a table |
| `DISTINCTCOUNT()` | Count unique values |
| `AVERAGE()` | Calculate a column average |
| `SUMX()` | Iterate over a table, evaluate an expression per row, and sum the results |

## `SUM()` vs. `SUMX()`

`SUM(Column)` adds the values already present in a column.

`SUMX(Table, Expression)` evaluates an expression for every row in the table and then adds those row-level results. It is useful when the calculation must happen before aggregation.

Example:

```DAX
Revenue =
SUMX(
    Sales,
    Sales[Quantity] * Sales[Unit Price]
)
```

## `CALCULATE()`

`CALCULATE()` evaluates an expression after modifying the filter context.

```DAX
Entire Place Listings =
CALCULATE(
    COUNTROWS(Listings),
    Listings[room_type] = "Entire place"
)
```

## Calculated column: reviews per reviewer

```DAX
Reviews per Reviewer =
CALCULATE(
    COUNTROWS(Reviews),
    ALLEXCEPT(Reviews, Reviews[reviewer_id])
)
```

This gives each review row the total number of reviews associated with that reviewer.

## Cumulative reviewers pattern

```DAX
Cumulative Reviewers =
VAR CurrentReviews =
    MAX(Reviews[Reviews per Reviewer])
RETURN
    CALCULATE(
        DISTINCTCOUNT(Reviews[reviewer_id]),
        FILTER(
            ALL(Reviews[Reviews per Reviewer]),
            Reviews[Reviews per Reviewer] <= CurrentReviews
        )
    )
```

Use the reviewer-count column on the axis and the cumulative measure as the value. Confirm that the column and table names match your model.

## Concepts to revisit

- Row context and filter context
- Context transition
- `CALCULATE()` and filter modifiers
- `ALL()`, `ALLEXCEPT()`, `ALLSELECTED()`, and `REMOVEFILTERS()`
- Variables with `VAR` and `RETURN`
- Time intelligence
- Iterators such as `SUMX()`, `AVERAGEX()`, and `FILTER()`
- Relationship behavior and `RELATED()`
