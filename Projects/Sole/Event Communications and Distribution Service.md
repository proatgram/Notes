Event Communications and Distribution Service
=================
# Key Outlines
In the Event Communications and Distribution Service defined here, there consists of three parts, the [Broker](##broker), the [Publisher](##publisher), the [Subscriber](##subscriber), and a [Hybrid](##hybrid) of the two.  This uses a similar ideology to the Publish Subscribe System, using a combitnation of Topic and Message based filtering and delivery systems, but also adds more features to be as flexible and useful as possible.

This system will act as the main methods of communication between multiple entities in the Sole Project.

## Direct Messaging System
In a traditional Publish/Subscribe system implementing a broker, the Publisher and Subscriber are decoupled and have little to no idea of each others existence. In this system however, it is possible to directly request data from the Publisher and the Subscriber through metadata sent within each message. The message will be sent through the Broker, with relavent meta-data to signify the recipient, and then directly to the Publisher or Subscriber. This allows for messages and data to be published to a direct recipient, allowing faster communication, and easier data exchange between two parties.

## Message Broadcast System
Expanding and using parts of the [DMS](###direct-messaging-system), it also allows for our subscribers, to query data from recievers that might happen to have the data requested, a similar idea to IP Multicast. This could be data within specific coordinates, etc. This would make it even easier to initiate data exchanges between two, or many parties.

## Publish Subscribe Ideology
This system however also functions as a standard Publish/Subscribe System, with an intermediate message [Broker](##broker) in the middle. This system will allow a Messanger to subcribe to or publish an Event, or a Message Content description, or a hybrid of the two. This allows the most flexibility when it comes to data exchange.

## Recieve Acknowledgements
When a Message gets published, indirectly or directly to one or more Messangers or Subscribers, it will include relavent data such that the Reciever can send an acknowledgement message in return if it is required. This is optional however, unless specified by the Message being sent. Such cases where an acknowledgement message must be sent upon recieving a message, could be a time sensative situation, in which blocking on the senders side happens until the sender knows for sure the message has been recieved correctly.

# Descriptions

## Broker
The Broker in this system contains all of the functionality to correctly route messages to their specific destination. This includes methods to:
 - Add a message onto the main queue
 - Send a Direct Message to a specific 
## Publisher

## Subscriber

## Hybrid
This is a Hybrid of a Publisher and Subscriber, which would most likely be used the most, as apposed to just a single publisher and single subscriber. This would inherit from both Publisher and Subscriber, allowing functionality of both.