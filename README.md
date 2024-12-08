
# Student Performance Analysis

This project focuses on analyzing student performance across various subjects. 
The objective is to categorize their performance as "Good", "Average", or "Bad" based on their grades and subject-specific full marks.

## What's New

- **Subject-Specific Full Marks**:
  - Arabic, Physics, Social Studies: Full mark = 25
  - Pure Mathematics and Mechanics: Full mark = 30
  - Advanced English: Full mark = 20
- Enhanced performance categorization function:
  - Dynamically calculates thresholds (60% for "Good", 40%-60% for "Average", below 40% for "Bad") based on full marks.
- Graceful handling of missing or non-numeric grades.

## Features

- Performance categorization for multiple subjects.
- Flexible logic to accommodate varying full marks for different subjects.
- Outputs categorized performance in a structured format.

## Dependencies

- Python 3.x
- pandas

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/Hosny-Mohammed/student_performance_analysis.git
   ```
2. Install the required dependencies:
   ```bash
   pip install pandas
   pip install matplotlib
   pip install seaborn
   ```
3. Open and run the Jupyter Notebook: `student_performance_analysis.ipynb`.

## Files

- `student_performance_analysis.ipynb`: Jupyter Notebook with the updated data processing and categorization logic.

## Example Code Snippet

The categorization function used:

```python
def categorize_performance(grade, full_mark):
    if isinstance(grade, (int, float)):
        if grade >= 0.6 * full_mark:
            return 'Good'
        elif grade < 0.4 * full_mark:
            return 'Bad'
        else:
            return 'Average'
    return 'Unknown'
```

Example of applying this function to subject marks:

```python
df['performance_arabic'] = df['mark_arabic'].apply(lambda x: categorize_performance(x, 25))
df['performance_math'] = df['mark_math'].apply(lambda x: categorize_performance(x, 30))
df['performance_physics'] = df['mark_physics'].apply(lambda x: categorize_performance(x, 25))
# ... repeat for other subjects ...
```

## Example Output

| Name      | Arabic Performance | Math Performance | Physics Performance | ... |
|-----------|--------------------|------------------|---------------------|-----|
| Student A | Good               | Average          | Bad                 | ... |
| Student B | Average            | Good             | Average             | ... |

## Contribution

Contributions are welcome! Submit issues or pull requests to improve this project.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
