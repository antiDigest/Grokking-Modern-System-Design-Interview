# Quiz on the Blob Store's Design
```
1. (Select the two most suitable options.) What is a blob store best suited for?.

A)
Storing a huge amount of data

B)
Storing unstructured data

C)
Storing structured data
```

```
2. What is the core component of the blob store, according to the design lesson?

A)
The master node

B)
A load balancer

C)
A monitoring mechanism
```

```
3. (Select all that apply.) What does the master node contain?

A)
Data bytes

B)
Blob to chunks mappings

C)
Chunks to data node mappings
```
```
4
The garbage collection process runs at the _________.

A)
master node

B)
data node

C)
monitoring system
```

```
5. Which technique is used to list a large number of blobs?

A)
Partitioning

B)
Replication

C)
Pagination
```

```
6. Which of the following is an indicator used in pagination?

A)
Continuation token

B)
Offset
```

```
7. (True or False) The blob store supports a hierarchical structure of data.

A)
True

B)
False
```

```
8. Garbage collection is used for _________.

A)
real-time latency optimization

B)
capacity optimization
```

```
9. How do we achieve availability?

A)
With synchronous replication within a storage cluster

B)
With asynchronous replication along the data center and different regions

C)
Both A and B
```

Answers
```
1. (Select the two most suitable options.) What is a blob store best suited for?. (A)(B)

A)
Storing a huge amount of data

B)
Storing unstructured data

C)
Storing structured data

Explanation
Blob store is best suited for storing massive amounts of unstructured data.
```

```
2. What is the core component of the blob store, according to the design lesson? (A)

A)
The master node

B)
A load balancer

C)
A monitoring mechanism
```

```
3. (Select all that apply.) What does the master node contain? (B)

A)
Data bytes

Explanation
The data bytes are stored on the data nodes. Metadata node just contain the mappings not the original data bytes.

B)
Blob to chunks mappings

C)
Chunks to data node mappings
```
```
4
The garbage collection process runs at the _________. (B)

A)
master node

B)
data node

C)
monitoring system
```

```
5. Which technique is used to list a large number of blobs? (C)

A)
Partitioning

B)
Replication

C)
Pagination
```

```
6. Which of the following is an indicator used in pagination? (A)

A)
Continuation token

B)
Offset
```

```
7. (True or False) The blob store supports a hierarchical structure of data. (B)

A)
True

B)
False

Explanation
It is a flat storage.

```

```
8. Garbage collection is used for _________. (A)

A)
real-time latency optimization

B)
capacity optimization
```

```
9. How do we achieve availability? (C)

A)
With synchronous replication within a storage cluster

B)
With asynchronous replication along the data center and different regions

C)
Both A and B
```



## How do we design a blob store system?
We have divided the design of the blob store into five lessons and a quiz.

1. [Requirements](../Requirements%20of%20a%20Blob%20Store's%20Design/): In this lesson, we identify the functional and non-functional requirements of a blob store. We also estimate the resources required by our blob store system.
2. [Design](../Design%20of%20a%20Blob%20Store/): This lesson presents us with a high-level design, the API design, and a detailed design of the blob store, while explaining the details of all the components and the workflow.
3. [Design considerations](../Design%20Considerations%20of%20a%20Blob%20Store/): In this lesson, we discuss some important aspects of design. For example, we learn about the database schema, partitioning strategy, blob indexing, pagination, and replication.
4. [Evaluation](../Evaluation%20of%20a%20Blob%20Store's%20Design/): In this lesson, we evaluate our blob store based on our requirements.
5. [Quiz](../Quiz%20on%20the%20Blob%20Store's%20Design/): In this lesson, we assess understanding of the blob store design.
Let’s start with the requirements of a blob store system.



## Move on to [Distributed Search](../../Distributed%20Search/System%20Design%20The%20Distributed%20Search/)