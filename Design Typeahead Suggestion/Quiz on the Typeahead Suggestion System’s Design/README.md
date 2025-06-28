# Quiz on the Typeahead Suggestion System’s Design
```
1
Which component is responsible for updating the trie offline in the design of the typeahead suggestion system?

A)
The assembler

B)
The suggestion service

C)
ZooKeeper

D)
None of the above
```

```
2
What is the purpose of MapRreduce in the design of the typeahead suggestion system?

A)
To disseminate data toward a database for storage

B)
To aggregate the prefix count

C)
To increase the number of required operations for optimization

D)
None of the above
```

```
3
Why do we aggregate the counts and update them offline in their respective shards?

A)
To enhance the write operations

B)
To provide accurate results to the user

C)
To minimize the latency of the read operations

D)
None of the above
```

```
4
(Select all that apply.) Why is the trie partitioned and stored on several servers?

A)
To reduce the load on a single server

B)
To store more data

C)
To increase the performance of the system

D)
None of the above
```

```
5
(Select all that apply.) The replication of the trie partition is required to enhance ________.

A)
fault tolerance

B)
the durability of the data

C)
the security of the data
```

Answers
1. (A)
2. (B)
3. (C)
4. (A) (C)
5. (A) (B)


## How will we design a typeahead suggestion system?
We’ve divided the chapter on the design of the typeahead suggestion system into six lessons:

1. [Requirements](../Requirements%20of%20the%20Typeahead%20Suggestion%20System’s%20Design/): In this lesson, we focus on the functional and non-functional requirements for designing a typeahead suggestion system. We also discuss resource estimations for the smooth operation of the system.
2. [High-level design](../High-level%20Design%20of%20the%20Typeahead%20Suggestion%20System/): In this lesson, we discuss the high-level design of our version of the typeahead suggestion system. We also discuss some essential APIs used in the design.
3. [Data Structure for Storing Prefixes](../Data%20Structure%20for%20Storing%20Prefixes/): In this lesson, we cover an efficient tree data structure called trie that’s used to store search prefixes. We also discuss how it can be further optimized to reduce the tree traversal time.
4. [Detailed design](../Detailed%20Design%20of%20the%20Typeahead%20Suggestion%20System/): In this lesson, we explain the two main components, the suggestions service and the assembler, which make up the detailed design of the typeahead suggestion system.
5. [Evaluation](../Evaluation%20of%20the%20Typeahead%20Suggestion%20System’s%20Design/): This lesson evaluates the proposed design of the typeahead suggestion system based on the non-functional requirements of the system. It also presents some client-side optimization and personalization that could significantly affect the system’s design.
6. [Quiz](../Quiz%20on%20the%20Typeahead%20Suggestion%20System’s%20Design/): In this lesson, we assess our understanding of the design via a quiz.
Let’s start by identifying the requirements for designing a typeahead suggestion system.


## Move on to [Design Google Docs](../../Design%20Collaborative%20Document%20Editing%20Service%20%20Google%20Docs/System%20Design%20Google%20Docs/)