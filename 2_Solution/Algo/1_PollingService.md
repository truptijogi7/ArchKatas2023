# Requirements
- Poll email looking for travel-related emails
- Filter and whitelist certain emails

## Solution
Once the user signup, they can connect their gmail/icloud/outlook with our Road Warrior app. Once they connect their account with our application, we will store auth key and periodically perform email polling.

Following access screen will be prompted to allow access when they connect their app 
![gmailConnectorReadAccess](/Assets/EmailReadAccess.png)

1. Authenticate and Connect to Registered Email Account
 
2. Retrieve Unread Emails in the past 1 week (Polling Frequency?)
 
3. Email Filtering (Keywords and Patterns)

    - Train Booking Detection  Keywords: TrainNumber, Train, Rail, Date, Time, Arrival, Departure

    -  Air Booking Detection Keywords: Flights, Air, Reservation, Confirmation, Airport, Date, Time, Arrival, Departure
    
    -  Car Rental Booking Detection: Car Registeration, Confirmation, Booking, Reference number, Date, Time

    - Hotel Booking Detection: Booking, Reference, Reservation, Accomodation, Bed, Breakfast, Date, Time, Check-in, Check out

4. Parsing Identified Emails

5. Data Storage

6. Mark Email as Processed

7. Repeat for all Emails in the range of past 1 week
 
8. Grouping and Presentation by Trip/Booking Id

9. Error Handling -Retrieval Errors/Failures

10. Update and Optimization

11. User Notifications
