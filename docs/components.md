# Components

Notifico consists of several key components that work together to provide its functionality. Here's an overview of the main components:

## Worker

The "worker" component is responsible for processing messages from the AMQP (Advanced Message Queuing Protocol) queue. Its main functions include:

- Reading messages from the AMQP queue
- Running the [Pipelines](pipeline.md)
- Sending the processed messages to different services as required

This component plays a crucial role in handling the asynchronous processing of notifications and ensures efficient distribution of workload.

## Web

The "web" component provides the administrative interface for Notifico. Its key features include:

- An admin panel for managing the system
- An associated API for the admin panel (currently in an unstable state)

This component allows administrators to monitor and control various aspects of the Notifico system through a user-friendly web interface.

## Ingest

The "ingest" component is responsible for receiving and queueing incoming notifications. Its primary functions are:

- Reading HTTP requests containing notification data
- Writing the received data to the AMQP queue for further processing

This component acts as the entry point for new notifications, ensuring they are properly queued for processing by the worker component.

## User API

The "userapi" component implements the user-facing API for Notifico. It provides various endpoints for user interactions, including:

- List-Unsubscribe functionality
- Other user-related operations (e.g., managing preferences, retrieving notification history)

This component serves as the interface between end-users and the Notifico system, allowing users to manage their notification settings and preferences.

Each of these components plays a vital role in the overall functionality of Notifico, working together to provide a robust and efficient notification system.