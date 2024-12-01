# Wikipedia Rare Diseases Pageviews Analysis

This repository contains data and scripts used in the analysis of Wikipedia page views for articles about rare diseases. The analysis covers a broad timeline and focuses on trends in mobile and desktop access, highlighting the variance in visibility and interest over months and years.

## Repository Structure

Below is the structure of the repository, showing how files are organized:

```plaintext
.
├── Documentation
│   ├── LICENSE.txt
│   └── README.md
├── Intermediate_Files
│   ├── rare-disease_monthly_cumulative_201507-202410.json
│   ├── rare-disease_monthly_desktop_201507-202410.json
│   └── rare-disease_monthly_mobile_201507-202410.json
├── Output_Files
│   ├── fewest_months_pageviews.png
│   ├── page_views_combined.png
│   └── top_peak_pageviews.png
└── Scripts
    └── data-512-homework_1.ipynb
```


## Data Schema

### Intermediate Files

1. **rare-disease_monthly_cumulative_201507-202410.json**
   - Contains cumulative monthly page views for all rare disease articles.
   - Fields: `date` (YYYY-MM format), `page_views` (integer).

2. **rare-disease_monthly_desktop_201507-202410.json**
   - Monthly desktop page views for rare disease articles.
   - Fields: `date` (YYYY-MM format), `page_views` (integer).

3. **rare-disease_monthly_mobile_201507-202410.json**
   - Monthly mobile page views for rare disease articles.
   - Fields: `date` (YYYY-MM format), `page_views` (integer).

### Output Files

1. **fewest_months_pageviews.png**
   - A graphical representation of the months with the fewest page views across all platforms.
   
2. **page_views_combined.png**
   - A combined graph showing trends in desktop and mobile page views over the selected period.
   
3. **top_peak_pageviews.png**
   - A chart highlighting the peak months of page views for rare disease articles.

## Scripts

- `data-512-homework_1.ipynb`: Jupyter notebook containing all the scripts used for processing the data and generating the output files.

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/your-repository.git

JSON Data Schema:

- **Article Title**: Key for each Wikipedia article.
    - **Data Structure**: String (e.g., `"Sickle_cell_disease"`)
  
- **Timestamp**: The month and year for the pageviews (formatted as YYYYMM).
    - **Data Structure**: String (e.g., `"202307"`)

- **Views**: Total number of pageviews for that article in the corresponding month.
    - **Data Structure**: Integer (e.g., `3456`)

## Example JSON Structure:

```json
{
  "Sickle_cell_disease": [
    {
      "timestamp": "202307",
      "views": 3456
    },
    {
      "timestamp": "202308",
      "views": 2987
    }
  ],
  "Cystic_fibrosis": [
    {
      "timestamp": "202307",
      "views": 1564
    },
    {
      "timestamp": "202308",
      "views": 1625
    }
  ]
}