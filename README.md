# Event Store

!(Event-Store.png)[Event Store]

---

The stream database built for Event Sourcing. EventStoreDB is an industrial-strength database technology used as the central data store for event-sourced systems. It is available open-source to run locally on most platforms or as SaaS through Event Store Cloud.

---

Event Sourcing is an alternative way to persist data in which all changes in a system are stored as an immutable series of events in the order that they occurred. The current state is derived from that event log.

This contrasts with state-oriented persistence that only keeps the latest version of the entity state; when changes occur in "traditional" database systems, the state is updated and the history, along with the reason for the change, is lost.

In event-sourced systems, whenever an action occurs that changes the state of a business entity (for example an order is marked as shipped), the system will publish an event to the stream describing what has happened (as per the example, the event might be OrderShipped). In EventStoreDB, additional metadata can also be stored in each event such as a timestamp, what action caused the event, and who performed that action.

The stream (or streams: EventStoreDB allows you to define and create many streams as required for your domain model) comprises a log of all events that have occurred, and by replaying them the current state can be derived. That can output the same end-result as in a traditional database, but it can also provide much more; you can perform additional tasks such as time travelling through the system and root cause analysis. And being immutable it provides one of the strongest methods for audit log available.

---
