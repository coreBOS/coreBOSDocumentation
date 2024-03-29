---
title: 'coreBOS Message Queue and Task Manager'
metadata:
    description: 'Documentation woes.'
    author: 'Joe Bordes'
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
taxonomy:
    category:
        - development
        - messagequeue
    tag:
        - message
        - queue
---

Following the marvelous work of [Martin Fowler](https://martinfowler.com/) in his book about [Enterprise Integration Patterns](https://martinfowler.com/books/eip.html) we have added a native Message Queue and Task Manager to coreBOS.

===

This is a developers enhancement which can be used to solve a wide range
of client requests elegantly and easily, taking coreBOS to another level
as a development​ framework and as an ever-growing business operating
system: **your core Business Operating System**.

Let's see how this works.

## Message Queue

coreBOS [has an abstract class](https://github.com/tsolucio/corebos/blob/master/include/cbmqtm/cbmqtm_manager.php) which defines the interface to work with the message queue. The methods are:

- sendMessage
- getMessage
- rejectMessage
- isMessageWaiting
- subscribeToChannel
- unsubscribeToChannel

So we need to implement a real class that instantiates these methods in order for the Message Queue to work.

We also have a message queue loader process. This process will look up two variables in the [coreBOS settings](../25.corebos_setting/item.md) store:

- file
- class

And create a Singleton named **corebos_mq** using that file and class name.

With this setup we can program using the **corebos_mq object**, sending and receiving messages without knowing how the implementation is done. We could be sending the message to a

- [RabbitMQ](https://www.rabbitmq.com/),
- [Kafka](http://kafka.apache.org/),
- [ActiveMQ](http://activemq.apache.org/)
- [NATS.io – Cloud Native, Open Source, High-performance Messaging](https://nats.io/)
- or simply to a database table.

By default, **coreBOS has a native Message Queue** implemented in the database. We did it this way because it would just work on all existing installs, but, as I describe above, you could implement more advanced and robust solutions easily.

Let's explain how coreBOS implements the Message Queue in the database.

### sendMessage

In order to send a message we need to define these parameters:

1. Channel
2. Producer
3. Consumer
4. Type
5. Share
6. Sequence
7. Expires
8. Deliver after
9. User
10. Message

#### Channel

The channel can be any string that both producer and consumer agree
upon. The producer will write messages on the channel and the consumer
will read (and delete) messages from the channel.

There are some special reserved channels by coreBOS which cannot be used freely.

#### Producer

The producer is a string uniquely identifying the creator of the message.

#### Consumer

The consumer is a string uniquely identifying the desired receptor of the message.

#### Type

Type is a string describing the contents or goal of the message.

The Message Queue itself does not use this value for anything. Some
values that are currently being used for some implementations are:

Command, Data, Event, Request, ...

#### Share

Is a string which accepts two values

1:M and PS

When a message is sent to the queue with share set to 1:M it will be be
written only once on the queue so it is consumed only by the intended
consumer.

When a message is sent to the queue with share set to PS, the message
will be written once per subscriber, effectively producing a mass
distribution messaging system. For example, if two or more processes
want to listen to the messages of another process they can subscribe to
the channel. When that producer emits a message with share PS all
subscribers will get the message.

#### Sequence

This is an integer that represents the sequence of this message from the producer.

The only use the message queue has of this value is to sort the messages
by it if there are more than one message waiting, but the message queue
does not guarantee order in the message delivery so any real sequencing
of messages must be done by the consumer.

#### Expires

This is the amount of seconds that the message can stay on the queue. After this time the message will be moved to the **cbInvalid channel** and marked as **invalid**.

#### Deliver After

Messages can be deferred to be sent in the future with this value. The
message will be accepted and put on the queue, the expire time will be
set to the number of seconds given added to the deliver after time.

The message will be totally ignored until the established time to deliver is reached.

#### User

The user that is sending the message. Currently not being used.

#### Message

The message itself is stored and returned as a string, so you can
serialize or json encode any object.

### getMessage

This method will ask the queue manager for a message on a channel by a
given producer and identifying itself as a unique consumer. If a message
exists it is returned and eliminated from the queue. If no message
exists false is returned.

### rejectMessage

Will put a message on the cbInvalid channel marked as invalid.

### isMessageWaiting

Returns true if there is a message waiting on the given channel by the
producer for the consumer.

### Subscribe and Unsubscribe

Will register or unregister a listener on a channel for a producer and
will define which task must be executed when a message arrives. This
task can be defined in one of two ways: as a file name and a function or
as a file name, a class name and a method.

## Task Manager

In conjunction with the Message Queue, the task manager is capable of
processing the queue and launching tasks.

I will describe how this works for the database implementation natively
included in coreBOS but note, once again, that this could be implemented
using any of the many existing solutions out there like
[Celery](http://www.celeryproject.org/), [Gearman](http://gearman.org/),
...

The default task manager in coreBOS is incredibly simple, consisting of
an infinite loop that looks for messages on the queue for all
subscribers​ and launches the defined task when one arrives.

The task manager is an independent process that must be launched or
initiated manually with the "run" command like this:

```shell
cd your_corebos_install_top_directory
php include/cbmqtm/run.php -d
```

This will run forever in an infinite loop that, on every iteration of
the loop will check and expires messages accordingly. If a message must
be delivered it will launch the indicated tasks for all subscribers so
they can consume the messages.

This is implemented using the OSS [PHP-Daemon](https://github.com/shaneharter/PHP-Daemon) project
(thanks!!)

## Examples and Ideas

### Integrations

The messaging system is ideal for this type of work. We created an
integration with [HubSpot](https://www.hubspot.com/) and
[Act-On](https://www.act-on.com/) using this philosophy. The main idea
is to implement an event handler in coreBOS that catches creations,
modifications and deletes on records in the system and sends a message
to the queue with the event and all the relevant information.

The task manager sees the message and launches, in background, a
process, to actually send the information and keep it in
synchronization.

### Polling

Polling is not a very optimal way of solving business requirements,
specially in the current trend of eventing appearing everywhere, but
sometimes it is needed.

It turns out that accomplishing this with coreBOS message queue and task
manager is a trivial setup.

It is as simple as sending a message to be delivered at the next poll
beat. The task manager will wake up the process which will do its work
and then send itself another message to be delivered at the next launch
time (poll frequency).

This is really powerful because it makes it extremely easy to implement
different wake up scheduled depending on the business needs. For
example, if we get the request to not poll on the weekend we simply set
the deliver after date to Monday morning on the last Friday launch.

### Feedback for long running processes

 !!! This is a future development which I personally want to implement.

Mass editing can be a very long running process. Sending a request to
modify a couple of fields on 1000 records can take a long time.
Currently, coreBOS sends this request and waits for the process to end.
This can produce timeouts in the browser or, worse, on the webserver.

So,the idea is to modify mass edit to send a message with the work to be
done. Then the task manager will do the work in background so there is
no timeout issues and no blocking in the browser. The background task
will report its progress as messages on the queue which will be consumed
by a browser process that reads the messages and informs of the progress
on screen. This will probably be implemented using [server side events](../24.corebos_sse/item.md) and service workers.

### Logging

Send log messages to the queue and have some process read them and send
them to a specialized platform like [Elastic](https://www.elastic.co/)

## Comparing with Martin Fowler's proposal

I would like to end this description with a quick comparison to the
global view defined by Martin Fowler:

![Martin Fowler's Message Queue](mfmq.png?width=100%)

The **Message Channel** and the **Message** itself are the parameters on
each of the calls of each method.

**Pipes, Filters, Routers and Translators** do not exist in the default
implementation but they all could be easily created as tasks to push the
message along the queue to it's destination.

The **Message Endpoint** is simply the getMessage method.

 ! I look forward to seeing what you construct with this powerful new feature.

## References

- [Queues](http://queues.io/)
- [Martin Fowler](https://martinfowler.com/)
- [Enterprise Integration Patterns](https://martinfowler.com/books/eip.html)
