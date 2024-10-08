# data-512-homework_1

## Project Goal
This project aims to analyze the page views of Wikipedia articles related to rare diseases. The analysis focuses on identifying trends in desktop and mobile page views over time. The insights gathered can help researchers understand the public interest in these topics. The project generates datasets of desktop and mobile access for each article and visualizes specific trends, including:

. Maximum and minimum average pageviews for desktop and mobile access.
. Top 10 articles with the highest peak pageviews for desktop and mobile access.
. Articles with the fewest months of available data for desktop and mobile access.

The final output includes time series visualizations based on the datasets and offers insights into trends in user access to these rare disease-related articles.

## Data License and Terms of Use
The source data for this project is provided by the Wikimedia Foundation. The dataset is subject to the Wikimedia Foundation's [Terms of Use](https://foundation.wikimedia.org/wiki/Terms_of_use). The Wikimedia Foundation's Terms of Use apply to your dataset by requiring that you attribute any content from Wikimedia projects, ensuring that your work adheres to open licensing. Your dataset must follow applicable laws, refrain from violating copyrights, and maintain transparency, especially if using Wikimedia data for commercial purposes. Contributions or reuses must not violate privacy, intellectual property, or the integrity of Wikimedia's infrastructure. Compliance with these rules ensures lawful and ethical use of the information.

## API Documentation
- [Wikimedia API Documentation](https://www.mediawiki.org/wiki/API:Main_page)
- [Pageviews API Documentation](https://wikimedia.org/api/rest_v1/#/Pageviews%20data/get_metrics_pageviews_data)

## Intermediate and Final Output Files
- Intermediate Files:

    The following JSON files are generated during the dataset creation process:

    - rare-disease_monthly_mobile_<startYYYYMM>-<endYYYYMM>.json: Contains mobile access data for the specified range of months.
    - rare-disease_monthly_desktop_<startYYYYMM>-<endYYYYMM>.json: Contains desktop access data for the specified range of months.
    - rare-disease_monthly_cumulative_<startYYYYMM>-<endYYYYMM>.json: Contains cumulative data for both mobile and desktop access for the specified range of months.

    These JSON files store the pageviews for each article by month in the following format:

JSON Data Schema:

article_title: The Wikipedia article title.
timestamp: The month and year for the pageviews (format: YYYYMM).
views: The total number of pageviews for that month.

- Final Output Files:
    The following PNG files are generated as visualizations based on the datasets:

- max_min_avg_pageviews.png: Shows time series for the articles with the maximum and minimum average pageviews for desktop and mobile access.

- top_peak_pageviews.png: Shows time series for the top 10 articles by largest peak pageviews for both desktop and mobile access.

- fewest_months_pageviews.png: Displays the time series of the articles with the fewest months of available data for desktop and mobile access.

#### Data Schema for JSON Files:
Each JSON file uses the following schema for each article:

- **Article Title**: Key for each Wikipedia article.
    - **Data Structure**: String (e.g., `"Sickle_cell_disease"`)
  
- **Timestamp**: The month and year for the pageviews (formatted as YYYYMM).
    - **Data Structure**: String (e.g., `"202307"`)

- **Views**: Total number of pageviews for that article in the corresponding month.
    - **Data Structure**: Integer (e.g., `3456`)

Example JSON Structure:
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

### Data Schema for Output Files
- **fewest_months_time_series.png**
    - **Description**: This image file visualizes the time series data of Wikipedia articles with the fewest months of page view data.
    - **Schema**: The plot includes the following elements:
        - X-axis: Months (formatted as YYYY/MM)
        - Y-axis: Page views (indicating the availability of data for each article)
        - Legend: Differentiates between desktop and mobile data lines

## Known Issues and Special Considerations
- Incomplete Data: Some articles may have incomplete data, especially for mobile access or for older periods. This can be observed on the 'Visualization 1: Maximum and Minimum Average Page Views'.

- Pageviews Variability: Pageview data may not always reflect user engagement consistently. Anomalies in pageviews (spikes or troughs) may be caused by factors like external media coverage or bot activity.

- Data Updates: Wikimedia data updates regularly; thus, future analyses may produce different results if repeated at a later date.

- Missing Data for Zero Views: When an article has no views for a particular month, the month is not included in the resulting JSON file for that article. This means that the datasets will contain only months with recorded views. Users analyzing the data should be aware of this, as they may need to account for missing months when performing calculations or visualizations.

- Data Format and Processing: The timestamps in the datasets were fixed to follow the format YYYY/MM, with some malformed timestamps corrected to ensure proper chronological ordering in visualizations. Users should double-check the formatting in case new issues arise with additional data.

- Logarithmic Scale in Visualizations: Some of the visualizations, particularly those showing page views over time, use a logarithmic scale on the Y-axis. This was necessary to handle the wide range of page view counts across different articles. When interpreting these graphs, be aware that the log scale emphasizes relative changes rather than absolute differences.

- Handling Zero or Missing Views in Visualizations: In the visualizations, when articles had zero or negative views, those values were replaced with a small positive number (1e-10) to avoid issues with the log scale. These values do not represent actual traffic but were used to ensure that all data points could be plotted.

- API Throttling and Data Collection Delays: To avoid overloading the Wikimedia API, a delay was introduced between consecutive requests. This means the data collection process can be slow, especially when retrieving data for many articles. If you're running the script or expanding the dataset, be prepared for longer collection times.

## License and Attribution

This project reuses code from an example licensed under [Creative Commons Attribution 4.0 International License (CC-BY 4.0)](https://creativecommons.org/licenses/by/4.0/). The reused code can be found in [link to original source or repository].

Original code and API example were developed by Dr. David W. McDonald for use in the DATA 512 course at the University of Washington. Modifications were made to adapt the code for Wikipedia pageviews of rare diseases and custom visualizations.

## Attribution:
Original code  was developed by Dr. David W. McDonald for use in DATA 512, a course in the UW MS Data Science degree program.

Changes made:
- Adaptation of API requests to collect Wikipedia pageviews for specific articles.
- Adjustments in data processing and visualization for this project’s specific needs.
