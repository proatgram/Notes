Event Based Pub/Sub System
=================
## Key Outlines
In the Publisher/Subscribe System defined here, there consists of three parts, the [Broker](#Broker), the [Publisher](#Publisher), and the [Subscriber](#Subscriber). 

### Direct Messaging System
In a traditional Publish/Subscribe system implementing a broker, the Publisher and Subscriber are decoupled and have little to no idea of each others existence. In this system however, it is possible to directly request data from the Publisher and the Subscriber through metadata sent within each message. The message will be sent through the Broker, with relavent meta-data to signify the recipient, and then directly to the Publisher or Subscriber. This allows for messages and data to be published to a direct recipient, allowing faster communication, and easier data exchange between two parties.

## Broker

## Publisher

## Subscriber