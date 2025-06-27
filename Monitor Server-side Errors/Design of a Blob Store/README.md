# Design of a Monitoring System

## Requirements
Let’s sum up what we want our monitoring system to do for us:

- Monitor critical local processes on a server for crashes.

- Monitor any anomalies in the use of CPU/memory/disk/network bandwidth by a process on a server.

- Monitor overall server health, such as CPU, memory, disk, network bandwidth, average load, and so on.

- Monitor hardware component faults on a server, such as memory failures, failing or slowing disk, and so on.

- Monitor the server’s ability to reach out-of-server critical services, such as network file systems and so on.

- Monitor all network switches, load balancers, and any other specialized hardware inside a data center.

- Monitor power consumption at the server, rack, and data center levels.

- Monitor any power events on the servers, racks, and data center.

- Monitor routing information and DNS for external clients.

- Monitor network links and paths’ latency inside and across the data centers.

- Monitor network status at the peering points.

- Monitor overall service health that might span multiple data centers—for example, a CDN and its performance.

We want automated monitoring that identifies an anomaly in the system and informs the alert manager or shows the progress on a dashboard. Cloud service providers provide a health status of their services:

- AWS: https://health.aws.amazon.com/health/status
- Azure: https://status.azure.com/en-us/status
- Google: https://status.cloud.google.com/
## Building block we will use
The design of distributed monitoring will consist of the following building block:

Blob storage: We’ll use blob storage to store our information about metrics.
## High-level design
The high-level components of our monitoring service are the following:

- Storage: A time-series database stores metrics data, such as the current CPU use or the number of exceptions in an application.

- Data collector service: This fetches the relevant data from each service and saves it in the storage.

- Querying service: This is an API that can query on the time-series database and return the relevant information.

![High-level design of a monitoring system](./system.jpg)

Let’s dive deep into the components mentioned above in the next lesson.



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
