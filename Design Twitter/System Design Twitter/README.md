# System Design: Twitter

## Twitter
Twitter is a free microblogging social network where registered users post messages called “Tweets”. Users can also like, reply to, and retweet public tweets. Twitter has about 397 million users as of 2021 that is proliferating with time. One of the main reasons for its popularity is the vast sharing of the breaking news on the platform. Another important reason is that Twitter allows us to engage with and learn from people belonging to different communities and cultures.

![A user performs various operation on Twitter](./operations.jpg)

The illustration below shows the country-wise userbase of Twitter as of January 2022 (source: Statista), where the US is taking the lead. Such statistics are important when we design our infrastructure because it allows us to allocate more capacity to the users of a specific region, and traffic served from near specific users.

![Country wise userbase on Twitter](./stats.jpg)

## How will we design Twitter?
We’ll divide Twitter’s design into four sections:

1. [Requirements](../Requirements%20of%20Twitter’s%20Design/): This lesson describes the functional and non-functional requirements of Twitter. We’ll also estimate multiple aspects of Twitter, such as storage, bandwidth, and computational resources.
2. [Design](../High-level%20Design%20of%20Twitter/): In this lesson, we’ll discuss the high-level design of Twitter in this lesson. We also briefly explain the API design and identify the significant components of the Twitter architecture. Moreover, we will discuss how to manage the Top-k problem, such as Tweets liked or viewed by millions of users on Twitter.
3. [Detailed Design](../Detailed%20Design%20of%20Twitter/): In this lesson, we’ll discuss the high-level design of Twitter in this lesson. We also briefly explain the API design and identify the significant components of the Twitter architecture. Moreover, we will discuss how to manage the Top-k problem, such as Tweets liked or viewed by millions of users on Twitter.
4. [Client-side load balancers](../Client-side%20Load%20Balancer%20for%20Twitter/): This lesson discusses how Twitter performs load balancing for its microservices system to manage billions of requests between various services’ instances. Furthermore, we also see why Twitter uses a customized load-balancing technique instead of other commonly used approaches.
5. [Quiz](../Quiz%20on%20Twitter's%20Design/): Finally, we’ll reinforce major concepts of Twitter design with a quiz.
Let’s begin with defining Twitter’s requirements.
