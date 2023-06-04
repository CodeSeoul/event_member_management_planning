# Use Cases
This document describes key use cases of the event member management system. Note that this should be a highly dynamic document, as we will continuously add use cases as the system matures.

## Personas
This section describes the personas that will be used throughout the use cases.

### Anonymous Student - Sejong
Sejong is a college student studying computer science who is conscious about his privacy. Sejong wants to learn more programming by going to events, but he's suspicious of "free" organizations and abuse of his personal data.

### Career Changer - Suzy
Suzy is a marketing professional that wants to become a data scientist. She knows databases are important and has seen data scientists' reports, but she's never written any code. She has a strong statistics background and a technical mind, but she has only basic computer knowledge.

### Role Changer - Jiyoung
Jiyoung is a mid-level frontend engineer. She's very knowledgeable in Javascript and has used some NodeJS as part of her frontend development, but she doesn't know infrastructure or the more advanced aspects of server development. She wants to become a backend engineer because she believes there is more demand and higher salary. (Please note that this is not necessarily true of backend engineering. This is just an example scenario for someone in a technical role that wants to switch to a different technical role.)

### New Instructor - June
June is a senior backend engineer and has volunteered to help with events at CodeSeoul. He's very capable technically, but he has limited experience in teaching groups. He sees teaching as a way to improve his skills as a senior engineer and build his network. He doesn't have time or interest in scheduling events and logistics.

### Organizer - Beth
Beth is an organizer with CodeSeoul. She's an engineering manager and sometimes runs events directly, but her concerns are focused more on posting events easily and checking events' performance to see what types of events to prepare next. She's always on the lookout for frequent attendees that could become instructors or organizers.

### Admin - Jo
Jo is an admin of the event-member management system. He wants to manage users' access and audit various data to ensure the system is working properly.

## Cases

### 1. Anonymous Event Browsing

<table>
    <tr>
        <th>Index:</th>
        <td>1</td>
    </tr>
    <tr>
        <th>Name:</th>
        <td>Anonymous Event Browsing</td>
    </tr>
    <tr>
        <th>Persona:</th>
        <td><a href="#anonymous-student---sejong">Anonymous Student - Sejong</a></td>
    </tr>
</table>

#### Background

Sejong heard of CodeSeoul from a friend, but he doesn't want to sign up with any service. He wants to see what events are happening without submitting any info.

#### Steps

1. Sejong visits the CodeSeoul website.
2. He clicks the events page, bringing him to the event-member management system.
3. He sees a notification that the website doesn't use cookies, which puts him at ease.
4. He sees some upcoming events on the main page.
5. He sees an event related to his current classes called "SH: Making Your First Web Server with Spring Boot".
6. He clicks the event to see more details.
7. He reads about the event and decides he wants to go. 
8. He clicks the RSVP button, expecting a prompt to login.
9. A modal appears, asking if he intends to bring any guests, and if so, how many.
10. He doesn't select guests and clicks a button to indicate he is attending the event.
11. He receives confirmation that he has RSVPed.
12. Suspicious, he refreshes the page. He sees that it still recognizes him as RSVPed with no guests.
13. He checks his browser to see if the website used cookies to track him, and he only finds some local storage data that indicates he RSVPed with zero guests.