# O'Reilly Architecture Katas fall 2023

ArchKatas2023 - Next generation online trip management dashboard by The Road Warrior

This is a team submission for O'Reilly [Architecture Katas fall 2023](https://learning.oreilly.com/featured/architectural-katas/).

# Team Members:  
- [Srujana Shreevatsav](https://www.linkedin.com/in/srujanasrivatsav/)
- Akash Ranjan
- [Trupti Jogi](https://www.linkedin.com/in/trupti-jogi/)
- [Raj Dugad](https://www.linkedin.com/in/raj-dugad)


## Analysis
  - [Problem Statement](./1_Analysis/1_problem%20statement.md)
  - [Functional Requirements](./1_Analysis/2_functional%20requirements.md)
  - [Assumptions](./1_Analysis/3_assumptions.md)
  - [Technical Capability required of platform](./1_Analysis/4_technical%20Capability%20required%20of%20platform.md)

## Architecture
- [Actors & User roles](/2_Solution/1_actors-user-roles.md)
- [Architecture Characteristics](/2_Solution/2_architecture-characteristic.md)
- [Implicit & Desired Characteristics](/2_Solution/3_implicit-characteristics.md)
- [High-level Architecture](/2_Solution/4_high-level-architecture.md)

## Services & Algorithms
- [Email polling Algo](/2_Solution/Services/1_PollingService.md)
- [Email filter & whitelist Algo](/2_Solution/Services/2_EmailFilterAlgo.md)
- [Year End Summary Reports](/2_Solution/Services/3_Summary.md)
- [Reporting and Analytics Service](/2_Solution/Services/4_Analytics.md)

## Architecture Characteristic
The RoadWarriers App is designed to be a centralized dashboard for all the trips/bookings made by the traveller for air,train,car rental and Hotel bookings by interacting with various preferred travel agencies

The UI needs to be interactive and Rich and responsiveness on web and mobile device is high

The number of users per day 2M Weekly avergaing to approx 300k DAU and can go upto 15M at peak times like seasonal holidays,school vacations etc.Scale and Elasticity therefore are important to be factored into the design

(1) Availability - The platform must allow users to connect with each other at any time of day or night as the app is international. And 5 mins per month ~60 mins Annual downtime will needa highly available system of 99.99%.[Note :Not all services are critical and some microservices can be 99.9% available]

(2) Responsiveness - The platform must handle requests quickly enough load the web portal within 800 ms and mobile under 1 sec.

(3) Interoperability : Since the system interfaces with various airlines globally,rail networks,car rentals and social media API's,interoperability with systems that are both legacy and distributed with platform agnosticity needs to be built.

(4) Scalability and Elasticity based on the Weekly user activity numbers given and also if the portal becomes popular,international demand needs to be supported.

(5) Evolvability-Both the UI and interfaces need to be deisgned for future extendability and to support growth of the platform in the form of new regions/vendors/travel agencies onboarded.

## CAP

Availability of the platform to a large degree and critical functions like Trip detail viewing/Airline Gate changes or updates cannot be missed by any traveller
Consistency of user experience on both web and mobile platforms as well as consistency of the data writes/reads is important

## Capacity Planning
Cloud Infra from AWS/Azure/GCP planner.

## Logical View
![Logical Architecture](/Assets/Logical_Diagram.png)

## Physical View


## Dashboard Presentation:

Develop a user-friendly dashboard where users can view their trips.

Provide options to edit, delete, or add new bookings to the trip.

**User Preferences Storage**

Allow users to set preferences for how they want their trips grouped or presented on the dashboard.


**Data Extractor**

We will use a dictionary to search email as well as to group trip's which have similar trip id's together.

Extract relevant details from the identified emails, including:
Flight Dictionary (e.g., airline, flight number, departure, arrival, date, time).
Rail Dictionary (e.g., train name, departure, arrival, date, time).
Car rental Dictionary (e.g., rental agency, pickup, return location, date, time).
Hotel Dictionary(e.g. , ReservationId,Bed,Breakfast,City,Date,time).

<Link to Diagram/Algo>


**Data Storage**
We will then store the extracted travel booking data in a database which will be used for faster retrieval during Traveller Feed generation on dashboard. You may need separate tables for different types of bookings (air, rail, car).


**Trip Grouping**
We are proposing to implement a trip grouping algorithm that identifies bookings belonging to the same trip based on shared criteria (e.g., common dates, destinations,Traveller details).

For this 1. Group the bookings into trips and create a trip identifier(TraceId of Trip) that can be used across all microservices for tracking and tracability.
         2. Display each trip with a summary of the bookings (flights, trains, car rentals) and relevant details (dates, times, destinations) in a readable manner from the above DB.
         3.Check with the user if the displayed information is correct,else allow user to make changes and update the change into a database for a machine learning data model implementation in future.
          4.If trips are not visible,provide forms/fields to update the infomration manually.Implementing additional Machine Learning principles could bring value by adding more key value pairs to dictionaries and analysing frequent tarveller/destination lists to group trips in future.


**Pre-fetch Cache**
We also propose the use of a cache to pre fetch some of the trip information ahead of time.This can be a batch job running a few times a day and is configurable based on trip frequency and user preferences.

Static Information liek PNR,Name,Flight/Train Name,Travel Agency/Car rental name etc can be localised with language using CDN and localisation.
Dynamic information like Flight times/Gate chnages etc can be fetched on demand to reduce load time.

## Notifications and Alerts:
<Add link to Notification Service>
Different types of channels to notify traveller as gate change/airline delays/price changes need to be communicated to avoid poor CX.

So we have adopted an omni channel update method to ensure the notifications are not missed even when there is a network failure by choosing SMS as well.

Types Supported:
Android Push
IOS Push
SMS
EMail

Here we use a publish-Subscribe Pattern to support notifications from external API's /interfaces.
Once a provider sends notifications to Apple Push notification Service(APNS) using some device tokena nd payload,a remote service provided by Apple can be used to propogate the actual message to IOS devices.

For Android we use FireBase Cloud Messaging and for SMS we can use Twilio or NEXMO like third party of local mobile service provider of the country where the traveller is located.

Since we have primary email configured during registeration we can send the email both to primary and secondary emails(for avoiding single point of failure)

Rate Limiting 
To Avoid overwhelming the user with too many notifications via multiple channels,we can limit the notifications and in case of failure of delivery,resend logic can be applied.


## ADR

1. [ADR Template](/3_ADR/1_ADR.md)


## Deployment Strategy

![Deployment Diagram](/Assets/Deployment)

