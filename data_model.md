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

All entities should track timestamps for when they were created and when they were last updated.

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
A venue entity represents a physical location where an offline [event](#event) takes place. A venue has a name and address. Later, we may store information like the bookable hours and dates, but that can wait until a later iteration. 

A venue can also be tracked via several [map services](#map-service). When a venue is related to a map service, the relationship should include a direct link to viewing the venue on the map service.

## Map Service
A map service entity represents an online map service like Google Maps or Naver Maps. Map services are used for easily sharing map links of [venues](#venue) for users' preferred map service.

A map service can be related to multiple venus. The relationship should include a link to the venue on the map service.

## Member
A member entity represents a member in the community. Members have a username and email, which cannot be empty. They also optionally have a display name, phone number, image URL for their profile image, and a free-form short biography. (TODO: max lengths)

Members can mark attendance to [events](#event) through [RSVPs](#rsvp). 

Members can also link their [social media accounts](#sns-account) for easier login and to help correlate their attendance across [social media services](#sns-service).

## SNS Service
An SNS service entity represents some social network service like Meetup, Facebook, LinkedIn, or OnOffMix. An SNS service has a name and icon URL, which are both required.

SNS services can be connected to [members](#member) through [SNS accounts](#sns-account).

## SNS Account
An SNS account entity represents a [member](#member)'s account on some [social media service](#sns-service). It references a member and the SNS service, and it stores a link to the member's profile page on the service.

## Member Role
A member role entity represents the [permission](#permission)s set that a [member](#member) has within the event member management service. The specific roles and their permissions are still being determined. A member role requires a name and a description.

## Permission
A permission entity represents some set of actions within the event member management service that a [member](#member) can take. These include things like viewing events, creating events, viewing other members' information, and more.

Permissions are granted to members through [member roles](#member-role).
