# AnalyticsBackendSystemArchitecture
 Design A Google Analytic like Backend System. 
 
**Requirement**
 
We need to provide Google Analytic like services to our customers. Pls provide a high level solution design for the backend system. Feel free to choose any open source tools as you want.

The system needs to:

- [ ]  handle large write volume: Billions write events per day.

- [ ] handle large read/query volume: Millions merchants want to get insight about their business. Read/Query patterns are time-series related metrics.

- [ ] provide metrics to customers with at most one hour delay.

- [ ] run with minimum downtime.

- [ ] have the ability to reprocess historical data in case of bugs in the processing logic.


**Requirement Analysis**

*   Collection   : Collects user-interaction data.
*   Configuration: Allows you to manage how the data is processed.
*   Processing   : Processes the user-interaction data with the configuration data.
*   Reporting    : Provides access to all the processed data.


![Image description](https://res.cloudinary.com/littledata/w_554,c_fit/littledata-blog-images/2017/02/googleanalytics4comp.png)
