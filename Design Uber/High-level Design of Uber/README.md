# High-level Design of Uber
## Workflow of our application
Before diving deep into the design, let’s understand how our application works. The following steps show the workflow of our application:

1. All the nearby drivers except those already serving rides can be seen when the rider starts our application.

2. The rider enters the drop-off location and requests a ride.

3. The application receives the request and finds a suitable driver.

4. Until a matching driver is found, the status will be “Waiting for the driver to respond.”

5. The drivers report their location every four seconds. The application finds the trip information and returns it to the driver.

6. The driver accepts or rejects the request:

  - The driver accepts the request, and status information is modified on both the rider’s and the driver’s applications. The rider finds that they have successfully matched and obtains the driver’s information.

  - The driver refuses the ride request. The rider restarts from step 2 and rematches to another driver.
  
![Rides](./uber/1.jpg)
![Rides](./uber/2.jpg)
![Rides](./uber/3.jpg)
![Rides](./uber/4.jpg)
![Rides](./uber/5.jpg)
![Rides](./uber/6.jpg)
![Rides](./uber/7.jpg)

## High-level design of Uber
At a high level, our system should be able to take requests for a ride from the rider and return the matched driver information and trip information to the rider. It also regularly takes the driver’s location. Additionally, it returns the trip and rider information to the driver when the driver is matched to a rider.

![High-level design](./hld.jpg)

## API design
Let’s discuss the design of APIs according to the functionalities we provide. We’ll design APIs to translate our feature set into technical specifications.

We won’t repeat the description of repeating parameters in the following APIs.

### Update driver location
```
updateDriverLocation(driverID, oldlat, oldlong, newlat, newlong )
```

```
Parameter          Description

driverID           The ID of the driver

oldlat             The previous latitude of the driver

oldlong            The previous longitude of the driver

newlat             The new latitude of the driver

newlong            The new longitude of the driver
```

The updateDriverLocation API is used to send the driver’s coordinates to the driver location servers. This is where the location of the driver is updated and communicated to the riders.


### Find nearby drivers
```
findNearbyDrivers(riderID, lat, long)
```

```
Parameter       Description

riderID         The ID of the rider

lat             The latitude of the rider

long            The longitude of the rider
```
The findNearbyDrivers API is used to send the location of the rider for whom we want to find the nearby drivers.

### Request a ride
```
requestRide(riderID, lat, long, dropOfflat,dropOfflong, typeOfVehicle)
```

```
Parameter        Description

lat              The current latitude of the rider

long             The current longitude of the rider

dropOfflat       The latitude of the rider’s drop-off location

dropOfflong      The longitude of the rider’s drop-off location

typeOfVehicle     The type of vehicle required by the rider—for example, business, economy, and so on.
```
The requestRide API is used to send the location of the rider and the type of vehicle the rider needs.

### Show driver ETA
```
showETA(driverID, eta)
```

```
Parameter        Description

eta              The estimated time of arrival of the driver
```
The showEta API is used to show the estimated time of arrival to the rider.


### Confirm pickup
```
confirmPickup(driverID, riderID, timestamp)
```

```
Parameter      Description

timestamp      The time at which the driver picked up the rider
```
The confirmPickup API is used to determine when the driver has picked up the rider.

### Show trip updates
```
showTripUpdates(tripID, riderID, driverID, driverlat, driverlong, time_elapsed, time_remaining)
```

```
Parameter         Description

tripID            The ID of the trip

driverlat         The latitude of the driver

driverlong        The longitude of the driver

time_elapsed      The total time of the trip

time_remaining    The time remaining (extract the current time from the ETA) to reach the destination
```
The showTripUpdates API is used to show the updates of the trip, including the position of the driver and the time remaining to reach the destination.

### End the trip
```
endTrip(tripID, riderID, driverID ,time_elapsed, lat, long)
```
The endTrip API is used to end the trip.

## How will we design Uber?
There are many unanswered questions regarding Uber. How does it work? How do drivers connect with riders? These are only two of many. This chapter will design a system like Uber and find the answer to such questions.

We’ve divided the design of Uber into six sections:

1. [Requirements](../Requirements%20of%20Uber’s%20Design/): This lesson will describe the functional and non-functional requirements of a system like Uber. We’ll also estimate the requirements of multiple aspects of Uber, such as storage, bandwidth, and the computation resources.
2. [High-level Design](../High-level%20Design%20of%20Uber/): We’ll discuss the high-level design of Uber in this lesson. In addition, we’ll also briefly explain the API design of the Uber service.
3. [Detailed Design](../Detailed%20Design%20of%20Uber/): We’ll explore the detailed design of Uber in this lesson. Moreover, we will also discuss the working of different components used in designing Uber.
4. [Payment Service and Fraud Detection](../Payment%20Service%20and%20Fraud%20Detection%20in%20Uber%20Design/): We’ll learn how the payment system works in Uber design. Moreover, we’ll also discuss how we can catch different frauds related to payments in Uber-like systems.
5. [Evaluation](../Evaluation%20of%20Uber’s%20Design/): This lesson will explain how Uber can fulfill all the non-functional requirements through the proposed design.
6. [Quiz](../Quiz%20on%20Uber's%20Design/): We’ll reinforce major concepts of Uber design via a quiz.
Let’s go over the requirements for designing a system like Uber in the next lesson.