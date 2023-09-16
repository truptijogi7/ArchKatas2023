## Architecture Characteristic

The RoadWarriers App is designed to be a centralized dashboard for all the trips/bookings made by the traveller for air,train,car rental and Hotel bookings by interacting with various preferred travel agencies

The UI needs to be interactive and Rich and responsiveness on web and mobile device is high

The number of users per day 2M Weekly avergaing to approx 300k DAU and can go upto 15M at peak times like seasonal holidays,school vacations etc.Scale and Elasticity therefore are important to be factored into the design

![characteristics](/Assets/Arch_characteristics.png)


1. Availability - The platform must allow users to connect with each other at any time of day or night as the app is international. And 5 mins per month ~60 mins Annual downtime will needa  highly available system of 99.99%.[Note :Not all services are critical and some microservices can be 99.9% available]

2. Responsiveness/Performance - The platform must handle requests quickly enough load the web portal within 800 ms and mobile under 1 sec.

3. Interoperability : Since the system interfaces with various airlines globally,rail networks,car rentals and social media API's,interoperability with systems that are both legacy and distributed with platform agnosticity needs to be built.

4. Scalability and Elasticity based on the Weekly user activity numbers given and also if the portal becomes popular,international demand needs to be supported.

5. Evolvability-Both the UI and interfaces need to be deisgned for future extendability and to support growth of the platform in the form of new regions/vendors/travel agencies onboarded.

![characteristics](/Assets/architecture-styles-worksheet.pdf)
*Figure 1 Architecture Characteristics*
