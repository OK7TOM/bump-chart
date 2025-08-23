# 📊 Vega Bump Chart in Deneb

A customized Vega bump chart built in [Deneb](https://deneb-viz.github.io/) (Power BI visual). Based on Kerry Kolosko’s original work, this version uses **Vega** instead of Vega-Lite to enable **precise line rendering between data points**, as well as other enhancements for better readability and interactivity.

## ✨ Features

- ✅ Built in **Vega 6.1.2** for custom logic and edge rendering
- ✅ Ranks displayed on Y-axis for a true bump chart experience
- ✅ Color-coded categories using Tableau scheme
- ✅ Interactive tooltips showing:
  - Rank
  - Week
  - Category
  - Amount (formatted)
- ✅ Light-outline circular points for each data entry
- ✅ Labels centered on points for clarity
- ✅ Dual Y-axes and a bold, readable X-axis

## 📈 What It Shows

The chart visualizes **ranking trends over time** for various categories, based on their weekly performance or value. Each category is tracked across multiple weeks, with rank changes highlighted using connecting lines and labeled points.

---

## 🔧 Dataset Structure

The chart expects the following data columns:

| Field Name   | Type     | Description                        |
|--------------|----------|------------------------------------|
| `Week`       | Numeric  | Week number                        |
| `YearWeek`   | Text     | Concatenated Year-Week format      |
| `Category`   | Text     | Category name                      |
| `Rank`       | Numeric  | Rank of the category in the week   |
| `Amount`     | Numeric  | Amount (e.g., value, volume, etc.) |

> These are internally referenced as `__0__`, `__1__`, etc., in Deneb.

---

## ⚙️ Custom Enhancements

- **Edge Drawing**: Lines only appear between **consecutive weeks** per category.
- **Tooltip**: Customized tooltip using Vega signals for cleaner display.
- **Stroke Effects**: Edges are dashed lines, and point outlines have light opacity.
- **Axes**: Includes both left and right Y-axes for easier reading.
- **Localization**: Axis titles are generalized for reuse: `# Categories by value`.

---

## 🚀 How to Use

1. Open your Power BI report.
2. Add the **Deneb custom visual** (if not already installed).
3. Copy and paste the provided Vega JSON into Deneb.
4. Bind your dataset to match the expected structure.
5. Customize styling or tooltip logic as needed.

---

## 🧠 Known Issues / Notes

- Make sure `Week` is numeric (not string) to enable correct edge drawing.
- JSON parse errors may appear if invalid syntax is introduced in signal expressions.
- Category names must be unique and consistent across weeks.

---

## 👨‍💻 Author

**Tomáš Mudroch**  
Customized and extended the original Deneb bump chart by [Kerry Kolosko](https://vega.github.io/vega-lite/examples/bump_chart.html).

---

## 📄 License

MIT License. See [LICENSE](LICENSE) for more details.
