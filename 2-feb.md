# Azure Functions

Data Collection:

Data is primarily gathered using Azure Functions. In instances where APIs are too costly or unavailable, we create our own solutions using popular Python libraries like Scrapy, Splash, and BeautifulSoup.

- For manual data collection, we employ Azure Functions with blob triggers. Whenever the data collection team adds new information to a blob container, the function evaluates its uniqueness and integrates it with the main SQL-hosted data.

# DataBricks

### Data Management

- We use Databricks Workspace for managing and shaping the collected data to align with business relevance, following Microsoft's Madeleine system approach.

- Our focus is on building indices and conducting experiments on the dataset to extract meaningful insights. The centralized workspace facilitates collaboration, allowing analysts to work in their preferred languages: SQL, R, Python, or Scala.

- To avoid a maintenance-challenging mix of languages, each layer of our architecture is dedicated to a specific programming language. For example, the bronze and silver layers primarily use Python, while the presentation layer incorporates Python, R, and SQL.

- This strategy also enables us to create dynamic, up-to-date views for Power BI. By shifting more computational work to Databricks, Power BI serves primarily as a presentation layer. For quick analyses and small dashboards, Databricks alone suffices due to its built-in tool for creating comprehensive visuals for everyday needs.

# Using ML

Currently, we have the Union Data Forecasting Model capable of predicting trends a year in advance. This model handles data drift and uses statically chosen columns effectively.

As we continue training our team, the goal is to leverage more data for modeling and forecasting. We plan to conduct team experiments using MLflow in Databricks.
