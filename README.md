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


# Actors & User roles

Actors and their associated user roles for the next-generation online trip management dashboard:

    • Travelers (End Users):
      Travelers are the main users of the system. They use the platform to manage their travel reservations, view trip details, receive updates, and access various features such as sharing trip information across social medias and generating end-of-year summary reports.
      
    • System Administrators:
      System administrators are responsible for managing and maintaining the overall system. Their roles include ensuring system uptime, handling technical issues, and managing user accounts and access permissions.
      
    • RoadWarrior Help Desk:
      User Role: RoadWarrior Help Desk personnel assist travelers with any issues they encounter during their trips. They may provide support via the dashboard to resolve problems related to reservations, travel updates, or other travel-related concerns.
      
    • Transport Manager:
      User Role: The Transport Manager is responsible for managing reservations and updates for all modes of transportation, including airlines, car rentals, and trains. They interface with the system to ensure that travel information for all types of transport is accurately reflected in the dashboard. This role handles the coordination and synchronization of transportation-related data across various transport modes.
      
    • Accommodation Manager:
      User Role: The Accommodation Manager is responsible for managing hotel reservations and updates. They interact with the system to ensure that hotel-related travel information is accurately reflected in the dashboard.
      
    • (need or not ) Reservations (Booking Agents):
      User Role: Booking agents may use the system to create and manage reservations on behalf of travelers. They have the responsibility to add, update, or delete existing reservations manually when required.
      
      
    • Travel Analytics ( RoadWarriors):
      User Role:This role involves analyzing data collected by RoadWarriors, such as cancellation and update frequency, travel locations, and trends. The insights derived from this analysis can be used to improve the dashboard and enhance the travel experience for users.
      
   
    • Third-Party Travel Systems (e.g., SABRE, APOLLO):
      These systems interface with the travel management dashboard to provide real-time updates on flight, hotel, and car rental reservations. The dashboard communicates with these systems to ensure users have up-to-date travel information.
      
    • Preferred Travel Agency:
      The preferred travel agency is integrated into the system for quick problem resolution. Users can contact the agency through the platform for assistance with their travel-related issues.
      