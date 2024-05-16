# Power-BI

**There are three primary components to Power BI:**
- Power BI Desktop (desktop application)
- Power BI service (online platform)
- Power BI Mobile (cross-platform mobile app)
Power BI Desktop is the development tool available to data analysts and other report creators. While the Power BI service allows you to organize, manage, and distribute your reports and other Power BI items. Power BI Desktop is available to download for free either through the Windows store or directly online.

**Building blocks of Power BI**

The building blocks of Power BI are semantic models and visualizations. Create a semantic model and then use visuals to build a report. Let's explore these items in more detail and how they relate to the flow of Power BI.

**Create visualizations in a report**

In Power BI Desktop, when you create a visualization (also called visual), you add it to the canvas for a report page. Choose your visualizations to build pages in your report. It's ideal to keep each page simple with related data, so consumers can easily see the insights.

**Power BI is a low-code solution**, which means that you can "drag and drop" data field directly onto the canvas. Power BI will choose a visual for your data field. You can easily change between visuals for the same fields, and add or remove data fields to the visual.

**Create a dashboard**
In the Power BI service, you can also create dashboards after you've published a report. Dashboards consist of a single page made up of tiles. Add tiles to a dashboard by pinning a visual in a report to the dashboard. Tiles aren't interactive like visuals, so when a user interacts with the tile, they go to the underlying report for more information.

**Power BI Desktop has three views:**
- Report view: You can create queries to build compelling visualizations that you can share with others. You can arrange them as you want them to appear.
- Data view: See the data in your report in data model format, where you can add measures, create new columns, and manage relationships.
- Model view: Get a graphical representation of the relationships that are established in your data model and manage or modify them as needed.

**Power BI has multiple insights features that use artificial intelligence (AI):**

- Insights for reports: Analyzes data and finds anomalies and trends in your data as you interact with reports.
- Insights for individual visuals: Analyzes and explains the fluctuations of data points in visuals.
- Insights for dashboard tiles: Looks at the data being used to render that tile and presents them in interactive visuals.
- Quick Insights for datasets: Automatically generate data insights on a dataset in the Power BI service.
- AI Insights for data models in Power Query: Provide access to pretrained machine learning models from Azure Cognitive Services.

# Insights
The Insights pane currently shows three types of insights:
- Anomalies: Represents something that is out of the ordinary from what is expected. For example, a smart thermostat that suddenly reads the temperature as 100 F when it's typically 72 F would be considered an anomaly.
- Trends: Represents a pattern that is found in time-series datasets. For example, if a company’s sales are steadily increasing through the month of April that would represent a trend.
- Key Performance Indicator (KPI) analysis: Helps you evaluate the current value against a defined target. For example, a company might set a sales goal at 1.2 million, but currently they are at 1 million.

# Anomalies
An anomaly is an abnormality in time-series data, such as unexpected spikes and dips in the data. An algorithm computes a boundary around what is considered a normal or expected value. Any value found outside this boundary is marked as an anomaly.

There are three types of anomaly insights:
- Significant anomaly: The anomaly has a high score. Anomaly score indicates how far the point is from the expected range.
- Recent anomaly: The most recent anomaly in the measure.
- Anomaly summary: This insight type summarizes multiple anomalies in the measure.

When an anomaly in your data is flagged, Power BI runs an analysis across the different dimensions in your data model to look for spikes or dips in the measure that correlates to the anomaly. They're shown as possible explanations ranked by strength.


# Trends
A trend occurs when there's a prolonged increase or decrease in time-series data. There are a series of steps the Power BI algorithm uses to find meaningful trends. It first performs data smoothening, interpolation, and time-series sampling. The trends are then identified for statistical significance based on the slope and length of a change in value. The algorithm removes noise like seasonality and outliers. For example, if sales jump in December, the algorithm doesn't mark that as a noteworthy trend because it's common for sales to jump around the holidays.

There are four main trends flagged:
- Long trend: The trend is significant and is the longest trend within a single series or across multiple series in a visual.
- Steep trend: The trend is significant and is the steepest trend within a single series or across multiple series in a visual.
- Recent trend: The trend is significant and is the most recent trend within a single series or across multiple series in a visual.
- Trend reversal: Recent trend in a single series or across multiple series in a visual where the reversal is significant, compared to the previous trend segment.

# Select a storage mode
The most popular way to use data in Power BI is to import it into a Power BI semantic model. Importing the data means that the data is stored in the Power BI file and gets published along with the Power BI reports. This process helps make it easier for you to interact directly with your data. 

**The three different types of storage modes you can choose from:**

- Import - The Import mode allows you to create a local Power BI copy of your semantic models from your data source. You can use all Power BI service features with this storage mode, including Q&A and Quick Insights. Data refreshes can be scheduled or on-demand. Import mode is the default for creating new Power BI reports.
- DirectQuery - The DirectQuery option is useful when you don't want to save local copies of your data because your data won't be cached. Instead, you can query the specific tables that you'll need by using native Power BI queries, and the required data will be retrieved from the underlying data source. Essentially, you're creating a direct connection to the data source. Using this model ensures that you're always viewing the most up-to-date data, and that all security requirements are satisfied. Additionally, this mode is suited for when you have large semantic models to pull data from. Instead of slowing down performance by having to load large amounts of data into Power BI, you can use DirectQuery to create a connection to the source, solving data latency issues as well.
- Dual (Composite) - in Dual mode, you can identify some data to be directly imported and other data that must be queried. Any table that is brought in to your report is a product of both Import and DirectQuery modes. Using the Dual mode allows Power BI to choose the most efficient form of data retrieval.


**Simplify the data structure**

When you import data from multiple sources into Power BI Desktop, the data retains its predefined table and column names. You might want to change some of these names so that they are in a consistent format, easier to work with, and more meaningful to a user. You can use Power Query Editor in Power BI Desktop to make these name changes and simplify your data structure.

**Profile data in Power BI**

Profiling data is about studying the nuances of the data: determining anomalies, examining and developing the underlying data structures, and querying data statistics such as row counts, value distributions, minimum and maximum values, averages, and so on. This concept is important because it allows you to shape and organize the data so that interacting with the data and identifying the distribution of the data is uncomplicated, therefore helping to make your task of working with the data on the front end to develop report elements near effortless.

**Analytic queries**

An analytic query is a query that produces a result from a semantic model. Each Power BI visual, in the background, submits an analytic query to Power BI to query the model. The analytic query is written as a Data Analysis Expressions (DAX) query statement. However, you don't need to write a native DAX statement; you only need to configure report visuals by mapping semantic model fields.

**An analytic query has three phases that are implemented in the following order:**

Filter
Group
Summarize
