# O'Reilly Architecture Katas fall 2023

ArchKatas2023 - Next generation online trip management dashboard by The Road Warrior

This is a team submission for O'Reilly [Architecture Katas fall 2023](https://learning.oreilly.com/featured/architectural-katas/).

# Team Members:  
- Srujana Shreevatsav
- Akash Ranjan
- [Trupti Jogi](https://www.linkedin.com/in/trupti-jogi/)
- [Raj Dugad](https://www.linkedin.com/in/raj-dugad)


## Analysis
  - [Problem Statement](./Analysis/1_problem%20statement.md)
  - [Functional Requirements](./Analysis/2_functional%20requirements.md)
  - [Assumptions](./Analysis/3_assumptions.md)
   - [Technical Capability required of platform](./Analysis/4_technical%20Capability%20required%20of%20platform.md)

## Architecture
- [Actors & User roles](/Solution/actors-user-roles.md)
- [Architecture Characteristics](/Solution/architecture-characteristic.md)
- [Implicit & Desired Characteristics](/Solution/implicit-characteristics.md)
- [High-level Architecture](/Solution/high-level-architecture.md)


## Data Extractor

Extract relevant details from the identified emails, including:
Flight details (e.g., airline, flight number, departure, arrival, date, time).
Rail details (e.g., train name, departure, arrival, date, time).
Car rental details (e.g., rental agency, pickup, return location, date, time).

<Link to Diagram/Algo>
**Data Storage**
Store the extracted travel booking data in a database. You may need separate tables for different types of bookings (air, rail, car).


**Trip Grouping**
Implement a trip grouping algorithm that identifies bookings belonging to the same trip based on shared criteria (e.g., common dates, destinations).
Group the bookings into trips and create a trip identifier.

Display each trip with a summary of the bookings (flights, trains, car rentals) and relevant details (dates, times, destinations).

## Dashboard Presentation:

Develop a user-friendly dashboard where users can view their trips.

Provide options to edit, delete, or add new bookings to the trip.

## Notifications and Alerts:

Implement notifications/alerts to inform users when new bookings are detected or when trip details are updated.
![Notification](/Assets/Notification%20Draft.png)
## User Preferences:

Allow users to set preferences for how they want their trips grouped or presented on the dashboard.

## CAP

Availability of the platform to a large degree and critical functions like Trip detail viewing/Airline Gate changes or updates cannot be missed by any traveller
Consistency of user experience on both web and mobile platforms as well as consistency of the data writes/reads is important

## Capacity Planning
Cloud Infra from AWS/Azure/GCP planner.

## Logical View
![Logical Architecture](/Assets/Logical%20Arch)
## Physical View

## Deployment Strategy

![Deployment Diagram](/Assets/Deployment)

