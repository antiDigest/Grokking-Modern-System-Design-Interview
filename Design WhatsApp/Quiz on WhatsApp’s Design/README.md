# Quiz on WhatsApp’s Design


```
1
The WebSocket manager is responsible for which function?

A)
Routing data toward a user

B)
Maintaining the mapping between users and their WebSocket handlers

C)
Reconnecting users to blob storage

D)
None of the above
```

```
2
What happens to the message if it’s sent to an offline user?

A)
The message is discarded, and an error response is sent back to the sender.

B)
The message is forwarded to another user.

C)
The message is stored in a database for a temporary period unless the user becomes online.

D)
None of the above
```

```
3
Why can’t WhatsApp use the Mnesia database to store media files instead of using blob storage?

A)
Mnesia provides limited capacity.

B)
Blob store is optimized to store and retrieve large files.

C)
Mnesia is more costly than blob storage.

D)
None of the above
```

```
4
(Fill in the blank.) If a media file is shared and accessed multiple times, it’s stored in ________ from blob storage.

A)
Kafka

B)
the Mnesia database

C)
a CDN

D)
a MySQL database
```

```
5
(Fill in the blank.) WebSocket servers use cache to ________.

A)
store messages temporarily

B)
store messages permanently

C)
store mapping of users and their corresponding WebSocket handlers

D)
store metadata of each user
```

Answers

1. (B)
2. (C)
3. (B)
4. (C)
5. (C)


## How will we design WhatsApp?
We’ve divided the design of WhatsApp messenger into the following five lessons:

1. [Requirements](../Requirements%20of%20WhatsApp’s%20Design/): In this lesson, we’ll identify functional and non-functional requirements. We’ll also discuss resource estimations required for better and smooth operations of the proposed design of WhatsApp.
2. [High-level Design](../High-level%20Design%20of%20WhatsApp/): We’ll focus on the high-level design of our WhatsApp version. We’ll also discuss essential APIs for our WhatsApp design.
3. [Detailed Design](../Detailed%20Design%20of%20WhatsApp/): In this lesson, we’ll describe the design of our WhatsApp messenger in detail. Initially, we’ll explain the design of each microservice, including connection with servers, send and receive messages and media content, and group messages. In the end, the design of each microservice is combined into the detailed design of WhatsApp.
4. [Evaluation](../Evaluation%20of%20WhatsApp’s%20Design/): This lesson will explain how our version of WhatsApp fulfills non-functional requirements. We’ll also evaluate some trade-offs of our design.
5. [Quiz](../Quiz%20on%20WhatsApp’s%20Design/): Here, we’ll assess what we’ve learned in this chapter through a quiz.
Let’s start by discussing the requirements of our version of WhatsApp.

## Move on to [Design Typeahead](../../Design%20Typeahead%20Suggestion/System%20Design%20The%20Typeahead%20Suggestion%20System/)