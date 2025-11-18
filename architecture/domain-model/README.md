# Domain Model

This document describes the Domain Model underpinning the entire software application suite.

# About Domain Models

A domain is the sphere of knowledge or activity the software operates within. For example: banking, healthcare, logistics, healthcare, law enforcement or security systems.

Domains are described in terms of:

- [Sub-Domains](#sub-domains)
- [Bounded Contexts](#bounded-contexts)
- [Entities](#entities-and-value-objects) 
- [Value Objects](#entities-and-value-objects)
- [Aggregates and Root Aggregates](#aggregates-and-aggregate-roots)
- [Domain Events](#domain-events)
- [Behaviours in response to Domain Events](#behaviours-in-response-to-domain-events)


## Sub-domains

Within a domain, there may be one or more subdomains. For many businesses these sub-domains include payments, inventory, customer management and support.

## Bounded Contexts

Within a domain there may be one or more Bounded Contexts. A Bounded Context is a clear boundary around a specific part of the domain and will often have its own vocabulary of terms to define concepts within that domain. 

Bounded Contexts may also define the concepts and vocabularly used to communicate information between domains. This is often the case when integrating with external systems where both the external system and the domain in question need to communicate information across the system boundary.

Vocabularies defined within Bounded Contexts make up part of the Ubiquitous Language used to describe the system.

**See also:**

- [Bounded Contexts main page](./bounded-contexts/README.md)

## Entities and Value Objects

[Entities](./domain-objects/entities/README.md) and [Value Objects](./domain-objects/value-objects/README.md) are both types of Domain Objects:

[Entities](./domain-objects/entities/README.md)  have unique identities (i.e. and ID number of some sort) and change over time. In a relational database [Entities](./domain-objects/entities/README.md)  have primary keys and are held within a table for that specific entity type.

[Value Objects](./domain-objects/value-objects/README.md) are immutable, have no unique identity and are merely defined by their attributes. For example: a geolocation (defined by longditutde and latitude), a monetary value or a postal address.

In a relational database, [Value Objects](./domain-objects/value-objects/README.md) (or their properties) are stored as values within the tables used to store [Entity](./domain-objects/entities/README.md) types.

## Aggregates and Aggregate Roots

An aggregate is a cluster of domain objects that are treated as a single unit for the purpose of data persistence.

The aggreate root is the Entity type that ensures data consistency within the aggregate. In other words, saving the aggregate root will save all of its contained entities in a consistent state. By 'consistent' we mean in the sense of data consistency, as used in ACID transactions.

**See also:**

- [Aggregates and Root Aggregates main page](./domain-objects/aggregates/README.md)

## Domain Events

Domain events represent signficant events that occur in the business domain. For example, when an Order is placed an OrderPlaced event is generated. And when a Payment is received a PaymentReceived event is generated.

Other parts of the system will listen for such events and respond accordingly.

Domain Events help decouple business logic in various parts of the system. Use of Domain Events in an Event-Driven Architecture (EDA) will improve maintainability, facilitate rapid innovation and easier integrations within a product suite and platform and with external systems that communicate with components of the platform.

**See also:**

- [Domain Events main page](./domain-events/README.md)


## Behaviours in response to Domain Events

These are documented and specified in User Stories and implemented in code.
