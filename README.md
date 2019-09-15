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


https://www.google.com/url?sa=i&source=images&cd=&ved=2ahUKEwji98PrhtPkAhXB3mEKHYmrDS4QjRx6BAgBEAQ&url=https%3A%2F%2Fblog.littledata.io%2F2017%2F03%2F15%2Fhow-google-analytics-works%2F&psig=AOvVaw16lWz3mNX-EJuLCC9vNmqe&ust=1568644647160756
