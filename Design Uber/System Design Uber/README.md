# System Design: Uber
## What is Uber?
Uber is an application that provides ride-hailing services to its users. Anyone who needs a ride can register and book a vehicle to travel from source to destination. Anyone who has a vehicle can register as a driver and take riders to their destination. Drivers and riders can communicate through the Uber app on their smartphones.

![Uber](./Uber/1.jpg)
![Uber](./Uber/2.jpg)
![Uber](./Uber/3.jpg)
![Uber](./Uber/4.jpg)
![Uber](./Uber/5.jpg)
![Uber](./Uber/6.jpg)
![Uber](./Uber/7.jpg)


The illustration below shows the number of active users of Uber from the start of 2017 to 2020 (source: Statista):

![Monthly number of Uber's active users worldwide from 2017 to 2020(by quarter)](stat.jpg)

## How will we design Uber?
There are many unanswered questions regarding Uber. How does it work? How do drivers connect with riders? These are only two of many. This chapter will design a system like Uber and find the answer to such questions.

We’ve divided the design of Uber into six sections:

1. [Requirements](../Requirements%20of%20Uber’s%20Design/): This lesson will describe the functional and non-functional requirements of a system like Uber. We’ll also estimate the requirements of multiple aspects of Uber, such as storage, bandwidth, and the computation resources.
2. [High-level Design](../High-level%20Design%20of%20Uber/): We’ll discuss the high-level design of Uber in this lesson. In addition, we’ll also briefly explain the API design of the Uber service.
3. [Detailed Design](../Detailed%20Design%20of%20Uber/): We’ll explore the detailed design of Uber in this lesson. Moreover, we will also discuss the working of different components used in designing Uber.
4. [Payment Service and Fraud Detection](../Payment%20Service%20and%20Fraud%20Detection%20in%20Uber%20Design/): We’ll learn how the payment system works in Uber design. Moreover, we’ll also discuss how we can catch different frauds related to payments in Uber-like systems.
5. [Evaluation](../Evaluation%20of%20Uber’s%20Design/): This lesson will explain how Uber can fulfill all the non-functional requirements through the proposed design.
6. [Quiz](../Quiz%20on%20Uber's%20Design/): We’ll reinforce major concepts of Uber design via a quiz.
Let’s go over the requirements for designing a system like Uber in the next lesson.
