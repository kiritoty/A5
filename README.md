# 1. Authentication and Authorization

Date: 10/22/2020

## Status

Proposed

## Context

There are different operations for different users in the Streaming Wars project. Firstly, we need to identify the user to make sure who they say they are; if they are invalid users, we won’t let them use our system. Secondly, we need to get/set their role and ensure users can use only certain functions. For example, only studio manager can create_event() etc.

## Decision

We will implement an authentication and authorization system such as a login system to ensure the only valid user can use this system and a role mapping system to assign user permission.

## Consequences

We will implement Authentication and Authorization into the project which will let the valid user (verify by their username and password) using the system and access or modify events base on their permission.

## Acceptance criteria

Users should be login into our system by using a username and password. The manager should be able to create an event and offer events base on requirements. Users can only access the event.



# 2. Achievability

Date: 10/22/2020

## Status

Proposed

## Context

In the streaming War project, we are storing data as long as the system still running. But we need to delete data after three months due to legal/policy requirements. In the current system, there is no way or no easy way to remove data. Users will care about their data privacy and programmer will care about architecture design changes.

## Decision

We are planning to implement a database to store user_info, event_info, etc. We will be using SQLite since it’s a stable, cross-platform, and lightweight DB management system.

## Consequences

Adding a database management system will make delete data easier. We just need to add a timestamp when each data created and remove it base on the timestamp.  Not even the delete, it will also help us to manage all information much easier.

## Acceptance criteria

Delete unused data (inactive demo group/watch history/previous profit) after 90 days.

