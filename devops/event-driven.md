# Event-Driven Architecture / Services

Client sends a request to a gateaway service, which then talks to all the other services but not directly, but rather via `events` - events are messages saying that something has changed; this event is then sent to all the subscriberts of this message broker, who check if the event concerns them or not - for example, does an email service need to send a notification regarding the event to a user?

## Examples:

- Git
- Smalltalk
- React
- node.js
- game servers

## How is event-driven architecture different to the publisher-subscriber model?

- Events are timestamped and can be rewinded to previous state
- events are sent to an `event bus`
- each microservice stores the events received from the event bus in their own local db (this is optional but good for data persistence, and means the event bus can be freed of the expired events); this means the services don't have to communicate with each other all the time - they can just query their local dbs

## Advantages:

- availability
- easy rollback to a previous event in the event log history
- services are easily replaced - the event log/db can be replayed on the new service to make its state consistent with the replaced one's
- transaction guarantee: events can be set up to be sent `at least once` or `at most once` - number of retries depending on how important the event is, not retrying the non-crucial logic
- storing the intent of the event so that each service can perform appropriate action

## Disadvantages:

- if the outcome of an event is dependent on an outside service (like say sending an email via an external serivce) then replaying the events from the event log will lead to different responses (inconsistency)
- less control with events sent via an event bus than with request/response architecture - with request/response, we can specify how much time a request should take and exactly which service it should be sent to
- the event might not come into the queue in the event bus in the time specified for the desired response
- impractical ways of accessing events in the log: either by replaying from the start, or diff based, or by an undo action (undo until a particular point [although compacting events makes rolling back to the point of compaction easier])
- hidden flow that is difficult to debug - you have to chase the event through the services, event bus and all of the event's subscribers
- migration of all or any part of this system to a request/response architecture is not easy
