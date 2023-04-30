# Event Member Management Planning

This repository serves as the source of truth for planning and requirements of the event member management system.

## Background
Community groups often need to post their events across various social media networks. This is often a great deal of copying and pasting with minor edits. Tracking RSVPs across social media events is also manual effort that consumes a great deal of time yet is worth effort. Additionally, organizers need ways to identify which members come to which types of events in order to better gauge popularity and predict attendance for future events they may attend. Paid solutions exist to fulfill these needs, but many early communities lack the funds to pay for these services.

## Purpose
The Event Member Management System (which really needs a better name) is meant to allow community organizers to manage events across various social media and to get a better understanding of their members' attendance patterns without paying for a for-profit service.

This repository is meant to define requirements for the system regardless of software language or framework. For purposes of learning, we encourage anyone to implement these requirements in any method they desire, both in and out of CodeSeoul. Initially, CodeSeoul will target a single technical stack, but multiple, duplicate, even competing implementations are welcome.

## Key Features
* Basic sign up and login, along with basic user roles
* Admins can post events across major social media
* Admins can track RSVPs and attendance aggregated across social media
* Admins can track and report attendance over time to provide insight into better future events
* Community members can sign up directly and view their history
* Admins can prepare live streams for events

Do note that the key features may change as the system matures. This is intended to be a living document that will grow and evolve as the system and needs evolve.

## Detailed Requirements
All requirements are malleable. Pull requests and discussion via issues or [our Discord](https://discord.gg/HFknCs8) are always welcome. Also, we are not perfect. If you find something wrong or believe something could be done better, we'd love a pull request. That includes the manner in which we're even defining requirements and structuring this repository.

* [High-Level Feature List](high_level_feature_list.md)
* [Data Model](data_model.md)
* [Technical Architecture](technical_architecture.md)
* [User Personas](user_personas.md)
* [User Flows](user_flows.md)
* [Use Cases](use_cases.md)
* [Wireframes and Mockups](https://www.figma.com/file/NbkIW7ekM6RGtt8ezC7fPa/Event-Member-Management?node-id=0%3A1&t=3FE9oRpmDk9ku1FM-1)

## References
This is a list of other services that have similar features to what we're targeting. Note that many of these services have features far beyond what is intended for this sytem. The intent is not to directly compete with them across all features but to use them as inspiration for our core goals.

* [Cvent](https://www.cvent.com/)
* [Blerter](https://www.blerter.com/)
* [Eventscase](https://eventscase.com/)
* [Eventify](https://eventify.io/)

## Implementation Repositories
* [CodeSeoul frontend implemented with Svelte](https://github.com/CodeSeoul/event_member_management)
* [CodeSeoul backend implemented with Spring Boot](https://github.com/CodeSeoul/event_member_management_backend)
