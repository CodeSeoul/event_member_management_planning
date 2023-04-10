# Data Model
This document will describe the data entities that the Event Member Management System will manage. This is intended to be conceptual. While most descriptions will be from the perspective a relational database, implementations can freely use other storage models, such as document stores or key-value stores, provided they handle the required attributes and interactions between entities.

# Entities
* [Event](#event)
* [Series](#series)
* [RSVP](#rsvp)
* [Venue](#venue)
* [Member](#member)
* [SNS Service](#sns-service)
* [SNS Account](#sns-account)

## Event
An event entity represents a community event. 

An event can have a title (TODO: determine maximum length). It can also have a detailed description. An event starts at a specific date and time, and it lasts for some duration. An event can optionally have an image.

An event can be online or offline. If offline, it should include a [Venue](#venue). If online, it should include a link to the online attendance platform.

An event can optionally belong to a [Series](#series).

[Members](#member) can [RSVP](#rsvp) to an event. A member cannot have more than 1 RSVP for an event.

## Series
A series entity represents a collection of related and/or sequential [Events](#event). A series also has a name (TODO: max length). For now, that's all.

## RSVP
An RSVP entity represents a [member](#member)'s intent to attend or not attend an [event](#event). An RSVP references a member and an event. It also carries a state: attending, not attending, or interested in attending.

## Venue


## Member
## SNS Service
## SNS Account
## Member Role
