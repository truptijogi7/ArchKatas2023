# O'Reilly Architecture Katas fall 2023

ArchKatas2023 - Next generation online trip management dashboard by The Road Warrior

This is a team submission for O'Reilly [Architecture Katas fall 2023](https://learning.oreilly.com/featured/architectural-katas/).

# Team Members:  
- Srujana Shreevatsav
- Akash Ranjan
- [Trupti Jogi](https://www.linkedin.com/in/trupti-jogi/)
- [Raj Dugad](https://www.linkedin.com/in/raj-dugad)


## Contents
- [Introduction](#introduction)  
- [Business Case](#business-case)
    - [Requirements](#requirements)
    - [Technical Constraints](#technical-constraints)
- [Actors & User roles](#Actors-User-roles)

![characteristics](/Assets/architecture-styles-worksheet.png)
*Figure 1 Architecture Characteristics*

## Desired Architecture Characteristics
Here we map technical requirements to associated architecture characteristics, which are ordered by importance. 

## Business requirement

## Technical capability required of platform

## Architecture Characteristic

The RoadWarriers App is designed to be a centralized dashboard for all the trips/bookings made by the traveller for air,train,car rental and Hotel bookings by interacting with various preferred travel agencies

The UI needs to be interactive and Rich and responsiveness on web and mobile device is high

The number of users per day 2M Weekly avergaing to approx 300k DAU and can go upto 15M at peak times like seasonal holidays,school vacations etc.Scale and Elasticity therefore are important to be factored into the design

1. Availability - The platform must allow users to connect with each other at any time of day or night as the app is international. And 5 mins per month ~60 mins Annual downtime will needa  highly available system of 99.99%.[Note :Not all services are critical and some microservices can be 99.9% available]

2. Responsiveness/Performance - The platform must handle requests quickly enough load the web portal within 800 ms and mobile under 1 sec.

3. Interoperability : Since the system interfaces with various airlines globally,rail networks,car rentals and social media API's,interoperability with systems that are both legacy and distributed with platform agnosticity needs to be built.

4. Scalability and Elasticity based on the Weekly user activity numbers given and also if the portal becomes popular,international demand needs to be supported.

5. Evolvability-Both the UI and interfaces need to be deisgned for future extendability and to support growth of the platform in the form of new regions/vendors/travel agencies onboarded.

![characteristics](/Assets/Arch_characteristics.png)

## Implicit Characteristics
**Cost**     Since it is an international app with several integrations with travel agencies/partners,costs to integrate with the platform must be kept low.
**Security**  It is important that the application is secure from malicious attacks which could exploit vulnerable user locations/stalk individuals.

## Actors & User roles

Actors and their associated user roles for the next-generation online trip management dashboard:

  * Travelers (End Users):
      Travelers are the main users of the system. They use the platform to manage their travel reservations, view trip details, receive updates, and access various features such as sharing trip information across social medias and generating end-of-year summary reports.
      
  * System Administrators:
      System administrators are responsible for managing and maintaining the overall system. Their roles include ensuring system uptime, handling technical issues, and managing user accounts and access permissions.
      
  * RoadWarrior Help Desk:
      User Role: RoadWarrior Help Desk personnel assist travelers with any issues they encounter during their trips. They may provide support via the dashboard to resolve problems related to reservations, travel updates, or other travel-related concerns.
      
  * Transport Manager:
      User Role: The Transport Manager is responsible for managing reservations and updates for all modes of transportation, including airlines, car rentals, and trains. They interface with the system to ensure that travel information for all types of transport is accurately reflected in the dashboard. This role handles the coordination and synchronization of transportation-related data across various transport modes.
      
  * Accommodation Manager:
      User Role: The Accommodation Manager is responsible for managing hotel reservations and updates. They interact with the system to ensure that hotel-related travel information is accurately reflected in the dashboard.   
   
  * Third-Party Travel Systems (e.g., SABRE, APOLLO):
      These systems interface with the travel management dashboard to provide real-time updates on flight, hotel, and car rental reservations. The dashboard communicates with these systems to ensure users have up-to-date travel information.
      
  * Preferred Travel Agency:
      The preferred travel agency is integrated into the system for quick problem resolution. Users can contact the agency through the platform for assistance with their travel-related issues.

![Actor_usecase](/ArchDiagrams/Actor_usecase%20diagram.png)

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
## User Preferences:

Allow users to set preferences for how they want their trips grouped or presented on the dashboard.

## CAP

Availability of the platform to a large degree and critical functions like Trip detail viewing/Airline Gate changes or updates cannot be missed by any traveller
Consistency of user experience on both web and mobile platforms as well as consistency of the data writes/reads is important

## Capacity Planning
Cloud Infra from AWS planner.

## Users and Roles

## Logical View

## Physical View

## Deployment Strategy

Need a deployment Diagram

