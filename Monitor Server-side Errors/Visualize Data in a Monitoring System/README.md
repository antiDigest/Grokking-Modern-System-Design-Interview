# Visualize Data in a Monitoring System
Large data centers have millions of servers, and visualizing the health data for all of them is challenging. An important aspect of monitoring a fleet of servers is to know which ones are alive and which ones are offline. A modern data center can house many thousands of servers in a building. We can use a heat map to display information about thousands of servers compactly in a data center.

A heat map is a data visualization technique that shows the magnitude of a phenomenon in two dimensions by using colors.

## Using heat maps to troubleshoot
We’ll identify if a server is down by using heat maps. Each rack of servers is named and is sorted by data center, then cluster, then row, so problems common at any of these levels are readily apparent.

A heat map depicting the operational state of a large number of components is an effective method. The health of each component is indicated by the color of each cell in a big matrix. Nodes with green cells operate within permitted parameters, while nodes with red cells are nonresponsive on multiple tries.

Below, we have a heat map displaying the server’s state.

![Viewing servers in a data center using heat maps](./cluster.jpg)

We can use heat maps for the globally distributed systems and continuously share the health information of a server. We can use one bit (one for live, zero for dead). For 1,000,000 servers, we have 125 KB of data. We can quickly find out which server is down by the red color and focus on the problematic parts.

We can create similar heat maps to get a bird’s-eye view of any resource, like filesystems, networking switches, links, and so on.
## Summary
- Monitoring systems are critical in distributed systems because they help in analyzing the system and alerting the stakeholders if a problem occurs.

- We can make a monitoring system scalable using a hybrid of the push and pull methods.

- Heat maps are a powerful tool for visualization and help us learn about the health of thousands of servers in a compact space.



## How will we design a distributed monitoring system?
We’ve divided the distributed monitoring system design into the following chapters and lessons:

1. Distributed Monitoring
- [Introduction to Distributed Monitoring](../Introduction%20to%20Distributed%20Monitoring/README.md): Learn why monitoring in a distributed system is crucial, how costly downtime is, and the types of monitoring.
- [Prerequisites for a Monitoring System](../System%20Design%20Distributed%20Monitoring/README.md): Explore a few essential concepts about metrics and alerting in a monitoring system.
2. [Monitoring Server-side Errors](../../Monitor%20Server-side%20Errors/Design%20of%20a%20Blob%20Store/README.md)
- [Designing a Monitoring System](../../Monitor%20Server-side%20Errors/Design%20of%20aa%20Blob%20Store/README.md): Define the requirements and high-level design of the monitoring system.
- [A Detailed Design of the Monitoring System](../../Monitor%20Server-side%20Errors/Detailed%20Design%20of%20a%20Monitoring%20System/README.md): Go into the details of designing a monitoring system, and explore the components involved.
- [Visualize Data in a Monitoring System](../../Monitor%20Server-side%20Errors/Visualize%20Data%20in%20a%20Monitoring%20System/README.md): Learn a unique way to visualize an enormous amount of monitoring data.
3. [Monitor Client-side Errors](../../Monitor%20Client-side%20Errors/Focus%20on%20Client-side%20Errors%20in%20a%20Monitoring%20System/README.md)
- [Focus on Client-side Errors](../../Monitor%20Client-side%20Errors/Focus%20on%20Client-side%20Errors%20in%20a%20Monitoring%20System/README.md): Get introduced to client-side errors and why it’s important to monitor them.
- [Design a Client-side Monitoring System](../../Monitor%20Client-side%20Errors/Design%20of%20a%20Client-side%20Monitoring%20System/README.md): Learn to design a system that monitors the client-side errors.

In the next lesson, we’ll look at why monitoring is essential in a distributed system through an example. We’ll also look at the downtime cost of failures and monitoring types.
