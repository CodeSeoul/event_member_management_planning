# High-Level Feature List

Here's a short-form list of features to cover things until more detailed use cases and user flows are ready. This is not meant to be complete or comprehensive, but it's meant to at least partially unlock development. These are meant to be in order or priority/dependency, but the order may not be perfect. Also note that tasks don't necessarily need to be completed in order. Some higher priority tasks may be higher difficulty and can be completed later.

* Users should be able to register an account and login.
* There should be at least two user roles: user and admin. This may expand, so take care to not constrain things too much. New users should have the user role by default.
* Admins should be able to grant roles to other users.
* Admins should be able to post events to the system.
* When an admin posts an event, they should have the option to post to one or more of Meetup, Facebook, and LinkedIn.
* When an admin edits or deletes a posted event, the event should also be updated on the corresponding SNS services.
* When an admin posts an event, it should be announced in the `#announcements` channel in Discord.
* When posting an event, an admin can mark if the event should be a livestream. If the event is marked as a livestream, the system should schedule a YouTube livestream for the event.
* Admins should be able to link event video recordings of events after the event has completed.
* Admins should be able to see how many people have RSVPed to an event on each SNS service.
* Admins should be able to see comments from the various SNS services.
* Users should be able to see a list of the events happening next in time.
* Users should be able to see the details of an event when selected.
* Users should be able to RSVP to an event.
* Users should be able to propose events.
* Users should be able to vote on proposed events.
* Admins should be able to review, edit, and submit proposed events.
* Users should be able to link their SNS accounts to their Event Member Management account.
* When RSVPing to an event, a user should be auto-RSVPed to the event on their connected SNS accounts.
    * Users should be able to set their SNS accounts to auto-RSVP to events if they RSVP directly in the Event Member Management system or on one of their SNS accounts.
    * When users link their SNS accounts, they should have the option to opt-out of this behavior when linking.
* When listing events, users should be able to filter by dates, series, time slot, and tags.
* When SNS accounts without linked Event Member Management users RSVP to events, the system should record those SNS accounts.
* Admins should be able to view attendance rates of both registered and non-registered users along various dimensions, including SNS service, venue, time slot, and tags.
* Admins should be able to set a repeating schedule for events, including both when the event should occur and how far in advance to post an event.
