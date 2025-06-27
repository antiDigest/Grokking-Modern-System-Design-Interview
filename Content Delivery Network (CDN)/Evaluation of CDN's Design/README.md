# Evaluation of CDN's Design
## Evaluation
Here, we see how our design fulfills the requirements we discussed in the previous lessons. Our main requirements are high performance, availability, scalability, reliability, and security. Let’s discuss them all one by one.

### Performance
CDN achieves high performance by minimizing latency. Some of the key design decisions that minimize latency are as follows:
- Proxy servers usually serve content from the RAM.
- CDN proxy servers are placed near the users to provide faster access to content.
- A CDN can also be the provider of proxy servers located in the ISP or Internet exchange points (IXPs) to handle high traffic.
- The request routing system ensures that users are directed to the nearest proxy servers. We’ll have a detailed discussion on the request routing system in the next lesson.
- The proxy servers have long-tail content stored in nonvolatile storage systems like SSD or HDD. Serving from these resources results in a more negligible latency than we’d see from serving content from origin servers.

```
Long-tail
If we monitor the access frequency of our content over some time, we can see a trend where some content is read by many clients (for example, 20% of content asked by 80% of clients), and then there is a long list of the content that very few clients ask for. Such an access distribution is called a long-tailed distribution.
```
![Long-tail](./longtail.jpg)
- As was discussed previously, proxy servers can be implemented in layers where if one layer doesn’t have the content, the request can be entertained by the next layer of proxy servers. For example, the edge proxy servers can request the parent proxy servers. Placing proxy servers at specific ISPs could be the best option when most traffic comes from those ISP regions.


### Availability
A CDN can deal with massive traffic due to its distributed nature. A CDN ensures availability through its cached content that serves as a backup whenever the origin servers fail. Moreover, if one or more proxy servers in the CDN stop working, other operational proxy servers step in and continue to drive the web traffic. In addition, edge proxy servers can be made available through redundancy by replicating data to as many proxy servers as needed to avoid a single point of failure and to meet the request load. Finally, we can use a load balancer to distribute the users’ requests to nearby active proxy servers.

### Scalability
The design of CDN facilitates scalability in the following ways:

- It brings content closer to the user and removes the requirement of high bandwidth, thereby ensuring scalability.
- Horizontal scalability is possible by adding the number of reading replicas in the form of edge proxy servers.
- The limitations with horizontal scalability and storage capacity of an individual proxy server can be dealt with using the layered architecture of the proxy servers we described above.
### Reliability and security
A CDN ensures no single failure point by carefully implementing maintenance cycles and integrating additional hardware and software when required. Apart from failures, the CDN handles massive traffic loads by equally distributing the load to the edge proxy servers. We can use scrubber servers to prevent DDoS attacks and securely host content. Moreover, we can use the heartbeat protocol to monitor the health of servers and omit faulty servers. Real-time applications also build their own specified CDNs to prevent content leakage problems and securely serve content to their end users.
## Conclusion
Since its inception in the 1990s, the CDN has played a vital role in providing high availability and low-latency content delivery. Nowadays, CDNs are considered a key player in improving the overall performance of giant services.


## How will we design a CDN?
We’ve divided the design of CDN into six lessons:

- [Introduction to a CDN](../Introduction%20to%20a%20CDN/README.md): We’ll provide a thorough introduction to CDNs and identify the functional and non-functional requirements.
- [Design of a CDN](../Design%20of%20a%20CDN/README.md): We’ll explain how to design the CDN. We’ll also briefly describe the API design.
- [In-depth Investigation of CDN: Part 1](../In-depth%20Investigation%20of%20CDN%20Part%201/README.md): This lesson explains caching strategies and CDN architecture. Also, we’ll discuss various approaches to finding the nearest proxy server.
- [In-depth Investigation of CDN: Part 2](../In-depth%20Investigation%20of%20CDN%20Part%202/README.md): We’ll discuss how to make content consistent in a CDN and the deployment of proxy servers. We’ll also cover the custom and specialized CDN in detail.
- [Evaluation of CDN](../Evaluation%20of%20CDN's%20Design/README.md): This lesson will provide an evaluation of our proposed design.
- [Quiz on CDN System Design](../Quiz%20on%20CDN's%20Design/README.md): We’ll reinforce major concepts of CDN design with a quiz.
Let’s think about the solution to the discussed issues in the next lesson.