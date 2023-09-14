# O'Reilly Architecture Katas fall 2023

ArchKatas2023 - Next generation online trip management dashboard by The Road Warrior

This is a team submission for O'Reilly [Architecture Katas fall 2023](https://learning.oreilly.com/featured/architectural-katas/).

# Team Members:  
- Srujana Shreevatsav
- Akash Ranjan
- [Trupti Jogi](https://www.linkedin.com/in/trupti-jogi/)
- Raj Dugad


## Contents
- [Introduction](#introduction)  
- [Business Case](#business-case)
    - [Requirements](#requirements)
    - [Technical Constraints](#technical-constraints)

![characteristics](/Assets/architecture-styles-worksheet.png)
*Figure 1 Architecture Characteristics*

## Desired Architecture Characteristics
Here we map technical requirements to associated architecture characteristics, which are ordered by importance. 

## Business requirement

## Technical capability required of platform

## Architecture Characteristic

The RoadWarriers App is designed to be a centralized dashboard for all the trips/bookings made by the traveller for air,train,car rental and Hotel bookings by interacting with various preferred travel agencies

The UI needs to be interactive and Rich and responsiveness on web and mobile device is high

The number of users per day ~2M/7=300k DAU and can go upto 15M/7~2M on peak times like seasonal holidays,school vacations etc.Scale and Elasticity therefore are important to be factored into the design

(1) Availability - The platform must allow users to connect with each other at any time of day or night as the app is international. And 5 mins per month ~60 mins Annual downtime will needa  highly available system of 99.99%.[Note :Not all services are critical and some microservices can be 99.9% available]

(2) Responsiveness - The platform must handle requests quickly enough load the web portal within 800 ms and mobile under 1 sec.

(3) Interoperability : Since the system interfaces with various airlines globally,rail networks,car rentals and social media API's,interoperability with systems that are both legacy and distributed with platform agnosticity needs to be built.

(4) Scalability and Elasticity based on the Weekly user activity numbers given and also if the portal becomes popular,international demand needs to be supported.

(5) Evolvability-Both the UI and interfaces need to be deisgned for future extendability and to support growth of the platform in the form of new regions/vendors/travel agencies onboarded.

## Implicit Characteristics
**Cost**     Since it is an international app with several integrations with travel agencies/partners,costs to integrate with the platform must be kept low.
**Security**  It is important that the application is secure from malicious attacks which could exploit vulnerable user locations/stalk individuals.


## CAP

Availability of the platform to a large degree and critical functions like Trip detail viewing/Airline Gate changes or updates cannot be missed by any traveller
Consistency of user experience on both web and mobile platforms as well as consistency of the data writes/reads is important

## Capacity Planning
Cloud Infra from AWS planner.

## Deployment Strategy

Need a deployment Diagram





