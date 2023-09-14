Issue: Choosing a DB design for storing the trip details for a traveller.Some of the data is related like Traveller details but Trips consists of combination fo Air,Rail,Road and accomodations that are related by tarveller and trip Id but can have multiple routes to reach a destination,multiple hops via different modes of transport.We will need fast retrieval to load the dashboard and group the trip by all booking made.

       
Decision: Use combination of Relational and Graph(Vertices represent cities/destinations and nodes represent mode of travel and airlines/Rail Operators )
          Accomodation is also represented in similar manner with Vertices representing City and Nodes representing HotelName.

Status : Pending 

Assumptions: Can be Archived into any other NOSQL Db after the trip completes.Most of the Querying would be read only.

Constraints: Storing info in 2 Databases can cause Sync/Integrity issues.Also Costs for managing 2 databases will be higher than 1 single relational db.
