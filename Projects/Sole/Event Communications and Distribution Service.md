Event Communications and Distribution Service
=================
# Key Outlines
In the Event Communications and Distribution Service defined here, there consists of three parts, the [Broker](##Bboker), the [Publisher](##publisher), and the [Subscriber](##subscriber).  This uses a similar ideaology to the Publish Subscribe System, using a combitnation of Topic and Message based filtering and delivery systems, but also adds more features to be as flexible and useful as possible.

## Direct Messaging System
In a traditional Publish/Subscribe system implementing a broker, the Publisher and Subscriber are decoupled and have little to no idea of each others existence. In this system however, it is possible to directly request data from the Publisher and the Subscriber through metadata sent within each message. The message will be sent through the Broker, with relavent meta-data to signify the recipient, and then directly to the Publisher or Subscriber. This allows for messages and data to be published to a direct recipient, allowing faster communication, and easier data exchange between two parties.

## Request Broadcast System
Expanding and using parts of the [DMS](###direct-messaging-system), it also allows for our subscribers, to query data from recievers that happen to have the data requested. This could be data within specific coordinates, etc. 

# Descriptions

## Broker

## Publisher

## Subscriber