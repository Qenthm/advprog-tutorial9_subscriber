# Reflection

## a. What is AMQP?

AMQP stands for **Advanced Message Queuing Protocol**. It is an open standard protocol for message-oriented middleware. AMQP enables systems to communicate by sending messages between clients and servers (producers and consumers) in a reliable, platform-agnostic, and language-independent way. It is commonly used in message brokers like RabbitMQ to facilitate asynchronous communication between distributed systems.

## b. What does `guest:guest@localhost:5672` mean?

This is a connection string used to connect to an AMQP broker (like RabbitMQ).

- The **first `guest`** is the username used for authentication.
- The **second `guest`** is the password for that user.
- **`localhost`** refers to the local machine (the AMQP broker is running on the same computer).
- **`5672`** is the default port number for AMQP protocol communication.

So, `guest:guest@localhost:5672` means:  
Connect to an AMQP broker running on your own computer (localhost) at port 5672, using the username `guest` and password `guest`.

---

## Simulation: Slow Subscriber

### Screenshot

![RabbitMQ Queue Count Screenshot](slow.jpg)

### Why is the total number of queues as such?

The total number of queues in RabbitMQ depends on how many queues have been declared by all publishers and subscribers, including any test or default queues. In my machine, the total number of queues is **[replace_with_your_number]**. This number may differ from your machine (which is 20) due to differences in running services, test runs, or leftover queues from previous experiments. Each time a new queue is declared (for example, by running the subscriber or publisher), RabbitMQ creates it if it does not already exist.
