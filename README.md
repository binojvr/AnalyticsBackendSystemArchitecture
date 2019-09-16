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


![GA Functional Block](https://res.cloudinary.com/littledata/w_554,c_fit/littledata-blog-images/2017/02/googleanalytics4comp.png)


**Data Collection Backend API Design**

Analtics input data includes millions of concurrent event data coming from sources. The volume is huge and it comes in very fast rates from milliions of sources. Hence Data collection API  must be  higly scalable highly efficient microservice API. We have many architecture options for designing the microservice API. The most common is REST microservice. The REST depends on HTTP/1.1 protocol. We know that HTTP/1.1 highly inefecient when we compared with web socket or HTTP/1.2 protocol implementations. HTTP/1.x was fundamentally built over the principle that only one response can be delivered at a time. This led to response queueing and blocking, slowing down the TCP connection along with whole lot of other problems. Many these problems are solved by HTTP/1.2 though REST doesnt support it yet.  Moreover the request response interaction model of HTTP that REST uses makes it poor choice for the data collection backend API.

Another solution is RSocket is a new binary application-level protocol capable of reactive streaming. Its is transport agnostic and can be used on top of any transport protocol like TCP or even on top of HTTP/2 or WebSocket. From QPS, latency, CPU consumption, and scalability, RSocket performs better than many compteting microservice implementation like REST, grpc etc. RSocket has various interaction  which can be used for different Use cases.
*   request/response (HTTP Like)
*   request/stream (finite stream of many)
*   fire-and-forget (Kind of Async)
*   event subscription (infinite stream of many)

For our Data collection API, Fire and Forget Model is best suited. 


![RSocket Clound Native using Netify](https://d33wubrfki0l68.cloudfront.net/0c3c98aa547922a0dce36160ac9755c9f00e2439/64eac/assets/images/netifi-arch3.jpeg
)



![API Front End Design]https://github.com/binojvr/AnalyticsBackendSystemArchitecture/blob/master/Screenshot_2018-08-15-Proteus-Microservices-Platform-Netifi.png?raw=true）





