# Basics of event-driven services: the Publisher - Subscriber Model

Using the request-response architecture, you send requests to S2 and S0 asynchronously (as the order doesn't matter).

Downsides: `Strong Coupling` - S3 and S4 might need to send responses to S2 in order for the request to complete, which leads to `Failure Latency` - takes a long time for this request to fail. Data might become inconsistent if several places within this single request fail, and the request is resent while it's still awaiting the initial response.

The solution to this problem is the `Publisher - Subscriber Model` - instead of sending a request, a message is sent to a message broker like Kafka, which is then responsible for messaging S2; success message is sent to the client once the message has been lined up in the message broker; Kafka will then wait for S2 to come back up before sending the message. The message broker can message S2 and S0

## Advantages

- decoupling of the servers/dependencies
- simplifies interactions - single interface for communicating with all the slaves/servers
- transaction guarantees - the message broker will persist messages until they are delivered
- easily scalable - same message broker can have many servers registered/subscribed
- good for stuff like gaming where a lot of events are constantly sent and analytics updated

## Disadvantages

- poor consistency - transactions pending across services
- should not be used for mission-critical systems because of that (bad for finance)
- idempotency still required - request has to have an id so the same request re-sent can be ignored (for example, a withdrawal of funds running again due to transaction failure) but this is something that has to be coded by the staff and is not built-in to this system

This architecture is used by Twitter

[Antipatterns in using message brokers](antipatterns.md)
