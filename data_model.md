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

An event has an [Event State](#event-state), indicating the current status of the event.

An event can belong to zero or more [Event Schedule](#event-schedule)s. If an event has an event schedule, it should be posted according to the event schedule configuration.

An event can be online or offline. If offline, it should include a [Venue](#venue). If online, it should include a link to the online attendance platform.

An event can optionally have an [Event Video](#event-video), which can be either an online stream of the event or a recording of the event.

An event can optionally belong to a [Series](#series).

An event can have zero or many [Event Tags](#event-tag).

[Members](#member) can [RSVP](#rsvp) to an event. A member cannot have more than 1 RSVP for an event.

[Members](#member) can vote on proposed events via an [Event Vote](#event-vote). An event can have zero or more event votes.

An event must have an [Event Type](#event-type) that specifies what kind of experience attendees can have at the event.

## Event Tag
An event tag entity represents a tag for connecting related [Events](#event). An event tag just has a name (TODO: max length).

An event tag can belong to many events.

## Event State
An event state entity represents the status of an [Event](#event). It indicates if the event is proposed by a user, in draft by an admin, posted, or in the past.

## Event Schedule
An event schedule entity represents a repeating schedule that an [Event](#event) follows. 

The event schedule should support day of week and Nth day of month configurations (e.g. first Friday of the month). Quarterly and annually are infrequent enough that organizers should handle them manually. Events requiring more complicated repetition than this can use a combination of multiple event schedules.

An event schedule should also include a posting schedule: how far in advance an event should be posted. Note that when cross-posting to SNS, services like Meetup support ongoing schedules, so this should be accounted for.

## Event Vote
An event vote entity represents a [Member](#member)'s support for a user-submitted proposed [Event](#event). It only needs to track the member, event, and timestamp of the vote.

# Event Video
An event video entity represents a video of an [Event](#event). The video can be either a live stream or a recording of the event posted afterwards. The entity should include a link to the video and whether the video is a livestream or a recording. 

The entity should reference the event it belongs to.

## Event Type

An event type represents what kind of experience attendees can have at an event. This is effectively a lookup table. The current types of events follow:

* Presentation - There will be a presenter that will present on some topic and have discussion.
* Workshop - A presenter will introduce some topic and have some hands-on practice for attendees.
* Panel - A group of panelists will discuss topics and answer attendees' questions.
* Meeting - CodeSeoul leadership and additional attendees will discuss the group and future plans for it.
* Coworking - Attendees will work on projects individually or together. There may or may not be a unified goal, technology, or theme.
* Social - Attendees will meet to network and socialize. Usually, there is no strict agenda or objective.
* Study Group - An organizer will provide structure and guidance, and attendees will study a topic together.

## Series
A series entity represents a collection of related and/or sequential [Events](#event). A series also has a name (TODO: max length). For now, that's all.

## RSVP
An RSVP entity represents a [member](#member)'s intent to attend or not attend an [event](#event). An RSVP references a member and an event. It also carries a state: attending, not attending, or interested in attending.

## Venue
A venue entity represents a physical location where an offline [event](#event) takes place. A venue has a name and address. Later, we may store information like the bookable hours and dates, but that can wait until a later iteration. 

A venue can also be tracked via several [map services](#map-service). When a venue is related to a map service, the relationship should include a direct link to viewing the venue on the map service. Additionally, since map services don't always match addresses, the link between a venue and map service should alow overriding the official venue address.

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
