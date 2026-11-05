# Video Game Sales & Market Performance Analytics

An interactive Power BI business intelligence project analysing historical video game sales, platform and genre performance, publishers, regional sales, and critic scores.

**Author:** Mohammad Hummad Siddiqui  
**Tools:** Power BI Desktop, Power Query, DAX, Excel  
**Dataset:** Video Game Sales with Ratings (Kaggle)  
**Project type:** Descriptive and exploratory business intelligence

## Business problem

Publishers and platform owners need a clear view of historical performance across platforms, genres, publishers, and regions. This project transforms historical video game sales and ratings data into interactive dashboards to identify market leaders, understand regional differences, and explore factors associated with commercial performance.

This is descriptive and exploratory analysis. It is not a future-sales forecasting model, and relationships between critic scores and sales should not be interpreted as causal.

## Project objectives

1. Analyse total global video game sales and historical trends.
2. Identify leading platforms based on cumulative global sales.
3. Compare sales performance across game genres.
4. Identify publishers with the highest cumulative global sales.
5. Examine regional sales contributions and genre differences.
6. Explore the relationship between critic scores and global sales.

## Dataset overview

The project presentation identifies the source as Kaggle's *Video Game Sales with Ratings* dataset and reports a final cleaned row count of **16,719**.

Fields include:
- Categorical: Name, Platform, Genre, Publisher, Developer, Rating
- Numerical: regional sales, global sales, critic score, user score
- Time: Year of Release

Sales are measured in millions of units. The source data contains missing values and represents historical coverage rather than the current video game market.

## Data preparation

Power Query steps documented in the project presentation:
- Reviewed data types and corrected invalid release-year values.
- Handled missing and unknown categorical values.
- Investigated duplicates while preserving legitimate releases across platforms.
- Created a unique `ReleaseID`.
- Unpivoted regional sales columns into `Region` and `Regional_Sales`.
- Prepared fact and dimension tables for DAX calculations and interactive reporting.

## Data model

The presentation documents these tables:
- Fact tables: `FactGameSales`, `FactRegionalSales`
- Dimensions: `DimGame`, `DimRelease`, `DimPlatform`, `DimYear`, `DimRegion`
- A measures table to organise DAX calculations

Example measure documented in the presentation:

```DAX
Total Global Sales = SUM(FactGameSales[Global_Sales])
```

## Dashboards

### 1. Executive Overview
- KPI cards: Total Global Sales, Total Platforms, Total Publishers, Unique Games
- Global sales trend
- Leading platforms and genres
- Slicers for release year, platform, and genre

### 2. Sales & Regional Intelligence
- Regional sales comparisons
- Publisher and genre performance
- Critic score versus global sales scatter chart
- Slicers for platform, release year, genre, and region

## Findings reported in the project presentation

- Approximately **8,920.30 million units** in total global sales.
- Among the five platforms displayed, PS2 ranks first, followed by X360, PS3, Wii, and DS.
- Among the four genres displayed, Action ranks first, followed by Sports, Shooter, and Role-Playing.
- Among the five publishers displayed, Nintendo ranks first, followed by Electronic Arts, Activision, Sony Computer Entertainment, and Ubisoft.
- Sales vary considerably at similar critic scores, with a small number of high-sales outliers.

These are descriptive findings from the presentation and should be interpreted within the dataset's historical coverage and the categories displayed in the report.

## Key limitations

- The dataset contains missing values and has historical rather than current-market coverage.
- Sales represent units, not revenue or profit.
- Critic-score patterns do not establish that ratings cause higher sales.
- Rankings are limited to this dataset and the categories displayed.
- The analysis is descriptive, not predictive.

## Repository contents

```text
power-bi-video-game-sales-analytics/
├── README.md
├── Final Power BI Capstone Project.pbix
├── Power BI Capstone Project Presentation.pptx
├── docs/
│   ├── project-summary.md
│   └── resume-entry.md
└── screenshots/
    └── Add dashboard screenshots here
```

## How to explore

1. Download the `.pbix` file from this repository.
2. Open it using Power BI Desktop.
3. Use the slicers to explore different years, platforms, genres, and regions.
4. Review the presentation for the business context, data preparation, model design, findings, and limitations.

## Future improvements

- Add screenshots of both report pages to this repository.
- Document important DAX measures and model relationships.
- Add a reproducible data-cleaning or refresh workflow where source-data permissions allow.
- Extend the analysis with newer data and reliable revenue/profit measures.
- Explore statistical modelling of sales drivers as a separate future project.
