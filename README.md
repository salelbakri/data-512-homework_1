# data-512-homework_1

# README for Wikipedia Article Page Views Analysis

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

### Data Schema for Output Files
- **fewest_months_time_series.png**
    - **Description**: This image file visualizes the time series data of Wikipedia articles with the fewest months of page view data.
    - **Schema**: The plot includes the following elements:
        - X-axis: Months (formatted as YYYY/MM)
        - Y-axis: Page views (indicating the availability of data for each article)
        - Legend: Differentiates between desktop and mobile data lines

## Known Issues and Special Considerations
- Incomplete Data: Some articles may have incomplete data, especially for mobile access or for older periods, which could skew certain analyses.

- Pageviews Variability: Pageview data may not always reflect user engagement consistently. Anomalies in pageviews (spikes or troughs) may be caused by factors like external media coverage or bot activity.

- Mobile vs Desktop: The separation of mobile web, mobile app, and desktop access could result in certain datasets having fewer records.

- API Rate Limits: While gathering data from the API, rate limits may be hit if too many requests are made in a short amount of time. Proper throttling is required to prevent blocking.

- Data Updates: Wikimedia data updates regularly; thus, future analyses may produce different results if repeated at a later date.
