#system-design 

asynchronously perform tasks given from producers to consumers

messages are processed once by a single consumer

## Difference from [[pubub]]
[Pub-Sub vs. Message Queues](https://www.baeldung.com/pub-sub-vs-message-queues)
- it uses pubsub model
>Conversely, to message queues, in a pub-sub architecture we want all our consuming (subscribing) applications to get _at least 1_ copy of the message that our publisher posts to an exchange.

### mq

[![1-1](https://www.baeldung.com/wp-content/uploads/2021/07/1-1.png)](https://www.baeldung.com/wp-content/uploads/2021/07/1-1.png)

### pubsub

[![1-2](https://www.baeldung.com/wp-content/uploads/2021/07/4.png)](https://www.baeldung.com/wp-content/uploads/2021/07/4.png)

final comparison: [Pub-Sub vs. Message Queues | Baeldung](https://www.baeldung.com/pub-sub-vs-message-queues#comparison)