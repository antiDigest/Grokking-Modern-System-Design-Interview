# Focus on Client-side Errors in a Monitoring System
## Client-side errors
In a distributed system, clients often access the service via an HTTP request. We can monitor our web and application servers’ logs if a request fails to process. If multiple requests fail, we can observe a spike in internal errors (error 500).

Those errors whose root cause is on the client side are hard to respond to because the service has little to no insight into the client’s system. We might try to look for a dip in the load compared to averages, but such a graph is usually hard. It can have false positives and false negatives due to factors such as unexpectedly variable load or if a small portion of the client population is affected.

There are many factors that can cause failures that can result in clients being unable to reach the server. These include the following:

- Failure in DNS name resolution.
- Any failure in routing along the path from the client to the service provider.
- Any failures with third-party infrastructure, such as middleboxes and content delivery networks (CDNs).

![Server-side errors versus client-side errors](./server_client.jpg)

## Failures due to a routing bug
Let’s look at a real-world example of an error that impacted a large number of service customers, but the service wasn’t readily aware of it.

One of Google’s peer ISPs accidentally announced Internet routes that it wasn’t supposed to. As a result, the traffic of many of Google’s customers started routing through unintended ISPs and wasn’t reaching Google. Clients were frustrated because they weren’t able to reach Google, while Google might have been unaware of such problems right away because these issues didn’t happen on its infrastructure.

![BGP leak](./bgp_leak.jpg)

The above leak isn’t unique. Similar issues keep arising. Another such leakage happened on April 16, 2021, when an AS mistakenly announced over 30,000 BGP prefixes. This resulted in a 13 times spike in the inbound traffic to their network. However, an increase in influx was observed, and the problem was solved.

The impacted services’ monitoring systems might not catch the above events readily. Monitoring such situations is crucial so that the application remains available for all of its customers. Therefore, in the next lessons, we’ll go through methods that help us to monitor the situations mentioned above.



## How will we design a distributed monitoring system?
We’ve divided the distributed monitoring system design into the following chapters and lessons:

1. Distributed Monitoring
- [Introduction to Distributed Monitoring](../Introduction%20to%20Distributed%20Monitoring/): Learn why monitoring in a distributed system is crucial, how costly downtime is, and the types of monitoring.
- [Prerequisites for a Monitoring System](../System%20Design%20Distributed%20Monitoring/): Explore a few essential concepts about metrics and alerting in a monitoring system.
2. [Monitoring Server-side Errors](../../Monitor%20Server-side%20Errors/Design%20of%20a%20Blob%20Store/)
- [Designing a Monitoring System](../../Monitor%20Server-side%20Errors/Design%20of%20aa%20Blob%20Store/): Define the requirements and high-level design of the monitoring system.
- [A Detailed Design of the Monitoring System](../../Monitor%20Server-side%20Errors/Detailed%20Design%20of%20a%20Monitoring%20System/): Go into the details of designing a monitoring system, and explore the components involved.
- [Visualize Data in a Monitoring System](../../Monitor%20Server-side%20Errors/Visualize%20Data%20in%20a%20Monitoring%20System/): Learn a unique way to visualize an enormous amount of monitoring data.
3. [Monitor Client-side Errors](../../Monitor%20Client-side%20Errors/Focus%20on%20Client-side%20Errors%20in%20a%20Monitoring%20System/)
- [Focus on Client-side Errors](../../Monitor%20Client-side%20Errors/Focus%20on%20Client-side%20Errors%20in%20a%20Monitoring%20System/): Get introduced to client-side errors and why it’s important to monitor them.
- [Design a Client-side Monitoring System](../../Monitor%20Client-side%20Errors/Design%20of%20a%20Client-side%20Monitoring%20System/): Learn to design a system that monitors the client-side errors.

In the next lesson, we’ll look at why monitoring is essential in a distributed system through an example. We’ll also look at the downtime cost of failures and monitoring types.
