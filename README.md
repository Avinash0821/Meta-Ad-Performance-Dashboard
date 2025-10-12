# Meta-Ad-Performance-Dashboard
This repository contains a synthetic dataset for analyzing the performance of digital advertising campaigns. The data is structured across four related CSV files, detailing campaigns, the ads within them, the users who interact with the ads, and the specific interaction events.

This dataset is ideal for projects involving data analysis, data visualization, business intelligence, and building predictive models for ad performance.

## Dashboard Preview

Below is an example of a performance dashboard that can be built using this dataset. It provides a high-level overview of key performance indicators (KPIs) and visualizes trends across different dimensions.

## Dataset Description

The dataset is composed of four CSV files that can be joined to perform a comprehensive analysis.

### 1\. `campaigns.csv`

This file contains high-level information about each advertising campaign.

  * **`campaign_id`**: Unique identifier for the campaign.
  * **`name`**: The name of the campaign.
  * **`start_date`**: The date when the campaign started.
  * **`end_date`**: The date when the campaign ended.
  * **`duration_days`**: The total duration of the campaign in days.
  * **`total_budget`**: The total budget allocated to the campaign.

### 2\. `ads.csv`

This file contains specific details for each ad, linking them to a campaign.

  * **`ad_id`**: Unique identifier for the ad.
  * **`campaign_id`**: Foreign key linking to the `campaigns.csv` file.
  * **`ad_platform`**: The platform where the ad was displayed (e.g., Facebook, Instagram).
  * **`ad_type`**: The format of the ad (e.g., Video, Image, Stories, Carousel).
  * **`target_gender`**: The gender targeted by the ad (Male, Female, All).
  * **`target_age_group`**: The age group targeted by the ad.
  * **`target_interests`**: The user interests targeted by the ad.

### 3\. `users.csv`

This file contains demographic information about the users.

  * **`user_id`**: Unique identifier for the user.
  * **`user_gender`**: The gender of the user.
  * **`user_age`**: The age of the user.
  * **`age_group`**: The age group category of the user.
  * **`country`**: The country where the user is located.
  * **`location`**: The specific location (city/region) of the user.
  * **`interests`**: The interests of the user.

### 4\. `ad_events.csv`

This file is an event log that records every interaction users have with the ads.

  * **`event_id`**: Unique identifier for the event.
  * **`ad_id`**: Foreign key linking to the `ads.csv` file.
  * **`user_id`**: Foreign key linking to the `users.csv` file.
  * **`timestamp`**: The exact date and time the event occurred.
  * **`day_of_week`**: The day of the week the event occurred.
  * **`time_of_day`**: The part of the day the event occurred (e.g., Morning, Afternoon, Evening, Night).
  * **`event_type`**: The type of interaction (e.g., Impression, Click, Like, Share, Purchase).

## Schema and Relationships

The files are related in a way that allows for a full view of campaign performance, from budget allocation down to individual user interactions.

```
+---------------+      +---------+      +----------------+      +-----------+
|               |      |         |      |                |      |           |
|  campaigns.csv  |----->| ads.csv |----->|  ad_events.csv   |<-----| users.csv |
|               |      |         |      |                |      |           |
+---------------+      +---------+      +----------------+      +-----------+
    (1 to Many)          (1 to Many)        (Many to 1)
```

  * A `Campaign` can have multiple `Ads`.
  * An `Ad` can have multiple `Events`.
  * A `User` can generate multiple `Events`.

## Potential Analysis & Use Cases

This dataset enables a wide range of analyses. Here are a few examples:

#### Performance Metrics

  * **Click-Through Rate (CTR)**: `(Total Clicks / Total Impressions) * 100`
  * **Conversion Rate**: `(Total Purchases / Total Clicks) * 100`
  * **Purchase Rate**: `Campaign Budget / Total Clicks`
  * **Return on Ad Spend (ROAS)**: Requires revenue data, but purchase events can be used as a proxy for conversion value.

#### Analytical Questions

  * Which campaigns are the most cost-effective?
  * What is the best performing ad platform (Facebook vs. Instagram) or ad type (Video vs. Image)?
  * What is the demographic profile (age, gender, country) of users who are most likely to make a purchase?
  * During which time of day or day of the week do we see the highest user engagement?
  * Is there a correlation between user interests and the interests targeted by our most successful ads?

## Getting Started

1.  Clone this repository to your local machine.
2.  Load the CSV files into your preferred data analysis environment : Power BI.
3.  Join the tables using their respective keys (`campaign_id`, `ad_id`, `user_id`) to start your analysis.

## Contributing

Contributions are welcome\! If you find any issues with the data or have ideas for additional data points that could be included, please open an issue or submit a pull request.

