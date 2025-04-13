---
share: true
---
https://dev.to/sunilc_/everything-you-need-to-know-about-message-queues-a-complete-guide-1220

> [!info] Source:
> https://www.baeldung.com/cs/message-queues
## 1. Introduction

A response to a request in a real-world application is not always instantaneous. We often assume that our applications would process everything instantaneously, or in a REST API, we often believe that we discard all unsuccessful requests, but the reality is slightly different. We can often process these unsuccessful requests later, or we can also send responses asynchronously.

In this tutorial, we’ll take a look at how we can leverage message queues to achieve this.

## 2. Asynchronous and Synchronous Communication

**Asynchronous communication is a mode of communication where the sender and receiver are not required to be active simultaneously**. It is often referred to as the fire-and-forget model of communication. Emails are a good example of asynchronous communication. A person can choose to read all their emails instantaneously or accumulate them to be read later at once. Similarly, a sender can send an email and move on to other tasks, without expecting an instantaneous reply.

**A telephone call can be an example of synchronous communication, where the sender and receiver interact in real-time, requiring both parties to be actively present and engaged simultaneously.**

Here is a diagram to illustrate the difference between asynchronous and synchronous communication:

[![[undefineddocs/assets/img/43a53a330b9d015937e182d9a1aab1ab_MD5.webp|43a53a330b9d015937e182d9a1aab1ab_MD5.webp]]](https://www.baeldung.com/wp-content/uploads/sites/4/2023/08/asyncVsSyncCommunication.png)

## 3. Definition of Message Queues
We’ll start by understanding the meaning of messages. In the context of a real-world software application, a message represents a piece of information that the application needs to process. This piece of information could be processed by another system or it can be an actual payload, like files or metadata that trigger some processing in another sub-system. Queues help in processing these messages sequentially. **A message queue is like a buffer that receives messages in a specific order and forwards them to the concerned sub-system or application in the same order.**

Message queues decouple the sender and recipient, allowing them to operate independently and at their own pace. Consumers retrieve messages from the queue when they are ready to process them. They can retrieve and process messages independently and at their own pace, allowing for asynchronous processing.

## 4. Examples of Usage of Message Queues
Let’s try to understand the scenarios in which message queues can be used through an example. Let’s say we have a web form that requires some input. We might need to insert this data into a database or put it into another system for some marketing automation.

These tasks if done in sync, can hamper the user experience as they might add some latency or slowness to the process. Thus, we can treat the inputs as messages and utilize a queue to process these messages based on our requirements. Meanwhile, the user can be redirected to another screen, displaying a predefined acknowledgment message.

## 5. Common Terminologies in Message Queues
Let’s go through some common terms used while working with message queues:

### 5.1. Producer
**The producer, also known as the sender, generates and sends messages to the message queue.** It creates and publishes messages that contain data, requests, or tasks to be processed by the consumer. The producer’s role is to enqueue the messages into the message queue without waiting for an immediate response. A producer can be a software application, service, or any component that generates and sends messages.

### 5.2. Consumer
**The consumer, also known as the receiver, retrieves and processes messages from the message queue.** It performs the necessary actions or operations based on the content of the messages. This can involve data processing, executing tasks, triggering workflows, or generating responses. Consumers can be separate software applications, services, or components designed to process specific messages or perform particular actions.

### 5.3. Topic
**In the context of message queues, a topic refers to a mechanism that enables categorizing or grouping messages based on a specific subject or theme**. It allows consumers to selectively subscribe to and receive messages based on their interest in specific topics. Topics enhance the flexibility and efficiency of message queues by allowing producers to categorize and target their messages while enabling consumers to consume messages based on their specific interests selectively.

### 5.4. Message Broker
**In the context of message queues, a message broker is an intermediary component that facilitates the exchange of messages between producers and consumers.** It acts as a central hub or mediator within the message queue system, responsible for receiving messages from producers, storing them, and delivering them to the appropriate consumers based on specified routing and subscription rules.

## 6. Publisher-Subscriber Model in Message Queues
The [publisher-subscriber](https://www.baeldung.com/pub-sub-vs-message-queues) model, also known as the pub-sub model, is a messaging pattern that facilitates communication between multiple publishers and multiple subscribers. In this model, publishers are responsible for producing messages, while subscribers receive and consume the messages based on their interests or subscriptions.

Here’s a simplified diagram illustrating the publisher-subscriber model:

[![[undefineddocs/assets/img/74d0d00d9a54ea1532b48435edd80ad7_MD5.webp|74d0d00d9a54ea1532b48435edd80ad7_MD5.webp]]](https://www.baeldung.com/wp-content/uploads/sites/4/2023/08/pub_sub_model.png)

In this diagram, Publisher 1 and Publisher 2 generate messages and publish them to the message queue. The message queue functions as an intermediary and retains the messages until the subscribers consume them. The subscribers (Subscriber 1, Subscriber 2, and Subscriber 3) subscribe to specific topics or channels of interest within the message queue. The message queue then delivers relevant messages to each subscriber based on their subscriptions, guaranteeing they receive only the messages aligned with their interests.

The publisher-subscriber model allows for decoupling between publishers and subscribers. Publishers don’t need to have direct knowledge of the subscribers, and subscribers can receive messages from multiple publishers. It provides a flexible and scalable approach for distributing messages to interested parties in a loosely coupled manner.

## 7. Benefits of Using Message Queues
Message queues help in decoupling parts of an application. While we can have a part that accepts data from the user, another part can process the data. Thus, we can move away from a huge monolithic application to a smaller, modular approach in development. By breaking it into smaller modules, we can test each module separately, without having to worry about all other parts in a system.

Another benefit of decoupling is that different teams can work on different parts of the system in parallel and improve development times significantly. We can also improve scalability by allowing certain processing to happen async during high traffic, without affecting user experience.

## 8. Conclusion
In conclusion, message queues serve as a valuable tool for efficient and reliable communication in various applications. In this tutorial, we’ve looked at message queues, the common terminologies used in message queues, the publisher-subscriber model, and some benefits of using message queues.