# Quiz on the Sharded Counters' Design
```
1 What kind of problem would occur if our system created a counter with a few shards for a post from a user with one million followers?

A)
High read contention

B)
High write contention

C)
Users face delays on a read request

D)
Users get a quick response on the liked post
```

```
2 (Select all that apply.) What problem might arise if shards are selected in an order (sequentially) rather than randomly?

A)
The write request queue increases.

B)
Maximum shard utilization decreases.

C)
One-by-one selection of shards will take more time.

D)
The user will not get quick responses.
```

```
3 (Select all that apply.) Which situation needs a larger number of sharded counters to handle the traffic on YouTube?

A)
A video posted by a channel with millions of subscribers

B)
A video with a few likes over a long period of time

C)
A video with millions of views but a few dislikes

D)
Long videos posted by a channel with a few subscribers
```

Answers
1. (B) 
2. (A) (B) (D)
3. (A) (C)



## How will we design sharded counters?

We have divided the design of sharded counters into three lessons:

1. [High-level Design](../High-level%20Design%20of%20Sharded%20Counters/): We’ll discuss the high-level design of sharded counters in this lesson. In addition, we’ll also briefly explain the API design.
2. [Detailed Design](../Detailed%20Design%20of%20Sharded%20Counters/): This lesson will dive deeply into the design of sharded counters. Moreover, we’ll also evaluate our proposed design.
3. [Quiz](../Quiz%20on%20the%20Sharded%20Counters'%20Design/): We’ll review major concepts of sharded counters design with a quiz.
Let’s begin with the high-level solution sketch of sharded counters.


## Move on to [Concluding building blocks](../../Concluding%20the%20Building%20Blocks%20Discussion/Wrapping%20Up%20the%20Building%20Blocks%20Discussion/)