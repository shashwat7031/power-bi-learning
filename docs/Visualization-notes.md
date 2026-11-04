# Data Visualization Notes

Notes on choosing visuals and communicating insights in Power BI.

## Visual selection

| Visual | Useful for |
|---|---|
| Card | A single KPI or headline metric |
| Bar / column chart | Comparing categories |
| Line chart | Trends over time |
| Scatter plot | Relationships between numeric variables |
| Map | Geographic patterns when location data is reliable |
| Matrix / table | Detailed values and cross-category comparisons |
| Histogram / binned column chart | Distribution of a numeric variable |

## Dashboard design checklist

- Give the report a clear title and purpose.
- Keep the most important KPIs easy to find.
- Use consistent colors, fonts, and number formats.
- Label axes and units clearly.
- Avoid unnecessary visual clutter.
- Use slicers and filters intentionally.
- Check interactions between visuals.
- Make sure the report remains readable at normal screen size.
- Use tooltips and drill-through only when they add value.

## Number formatting

For a card that displays a value such as `182.024K`:

1. Select the card.
2. Open the Format visual pane.
3. Find the callout value / data label settings.
4. Set **Display units** to **None**.
5. Set decimal places as required.

## Storytelling

A useful dashboard observation should explain:

- **What happened?** State the pattern or comparison.
- **Where / for whom?** Identify the category, city, or segment.
- **Why it matters?** Explain the practical takeaway, without claiming causation unless the data supports it.

Keep observations tied to the dataset and report filters.
