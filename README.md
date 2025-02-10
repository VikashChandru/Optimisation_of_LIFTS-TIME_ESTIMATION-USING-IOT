# Optimisation_of_LIFTS-TIME_ESTIMATION-USING-IOT

This project tries to optimise the lift by checking whether there are people when the button is pressed and this is constanly checked so that if there is no one the lift wont stop at that floor ,we do this through PIR sensor(Personal infrared sensor) and to determine the time taken for the lift to reach you we have used Ultrasonic sensor and FSR (force sensitive resistor) and in order to see how the lift is optimised we have used Multimeter to monitor the change in energy .The lift time estimation is done through a ml model which keeps a track of all the values in the lift.The whole point of using the ml model is to make the lift provide better more precise time estimation based on the activity of the lift like in certain time stamps the lift might stop more frequently in certain stops.The whole project was done in TinkerCad software feel free to access it from here.ALL THESE WERE MADE WITH DESIGNING AN APP,IN MIND WHERE THE USER CAN USE AND SEE THE TIME ESTIMATION OF THE LIFT AND IT WILL SUGGEST WHETHER THE USER SHOULD WAIT FOR THE LIFT AND ALSO TELL WHETHER HE SHOULD TAKE THE LIFT AND IF HE TAKES SO WILL IT LEAD TO OVERWEIGHT OR NOT .IF ITS CURRENTLY OVERWEIGHT OR WILL LEAD TO OVERWEIGHT THE APP SUGGEST NOTS TO TAKE IT.

https://www.tinkercad.com/things/eZrI7aOquat-lift-optimisation-and-time-estimation?sharecode=QCOUa4dtwrpbX6FUJhbhBxr7DjjDqprS8yHxc4c4ubE

Here the Time Estimation is calculated through this formula 
    int floorsTravelled = abs(destinationFloor - currentFloor);
    float travelTime = floorsTravelled * baseTravelTimePerFloor * (1 + loadFactor) + accelerationTime + decelerationTime;

As per the project we have tried to adhere to the standards used in the lift industry(SEIS Lift standards)
For further queries please refer the other word document attached 

FEATURES OVERVIEW:
1. Overweight Condition (Lift Overweight)
Weight Threshold Check:
If the Force Sensor (FSR) detects a weight value that exceeds a specified threshold (weightThreshold = 700), the system will determine that the elevator is overloaded.
Lift Overweight Decision:
When the system detects an overweight condition (based on the FSR value), the elevator will be prevented from stopping or moving further. The decision "Lift Overweight" is made, and the elevator will not proceed to its destination or perform any further stops.
Action: The system will print the message: "Lift will not stop due to overload" to the serial monitor.
Prevention of Stops: The elevator will not continue or stop at any floors when the overweight condition is triggered.
2. Space Unavailability (No Space)
Space Availability Check:
The Infrared (IR) sensor value is used to determine if there is enough space in the elevator. The system uses the IR sensor to check if the available space in the elevator is sufficient for passengers.
Decision "Space Unavailable":
If the IR sensor value indicates that there is insufficient space (i.e., the value is below a threshold, such as spaceThreshold = 500), the elevator will decide that space is unavailable. The decision printed will be "Space Unavailable."
Action: If the space is unavailable, the elevator won't allow further movement, and no passengers can board. The system will wait for more space to become available.
3. Stop Conditions
Presence Detection at Stop Floors (PIR Sensor):
For each stop floor, the system checks the PIR sensor to determine whether a person is present at that floor. The decision logic includes:
If the PIR sensor detects a person (value HIGH), the elevator will stop at the current floor.
If no person is detected (value LOW), the elevator will skip that stop.
Decision "Stop at Floor":
When a person is detected at a stop floor, the elevator will stop, and the decision printed will be "Stop at Floor."
Action: The system increments the stop count and adds a stop delay (stopDelay = 3.0 seconds) to simulate the time spent waiting for the passengers to board or alight.
4. Overload and Space Unavailability Decision Logic
Overload Prevention:
When the weight measured by the FSR exceeds the threshold, the system stops further operations, ensuring the elevator won't move with an overloaded capacity.

The system outputs the message: "Lift Overweight" if the FSR value crosses the threshold.
Additionally, it will notify: "Lift will not stop due to overload" in the case of such a condition.
Space Unavailable Decision:
If the space inside the elevator is insufficient (detected by the IR sensor), the decision printed will be "Space Unavailable," and the elevator won't proceed with any further movement.

Normal Decision "Wait for Lift":
If there is enough space and no overload, and no specific passenger activity is detected, the system decides the elevator is ready to continue, and the printed message will be "Wait for Lift." This condition represents normal operation where the elevator is available for the next action.

5. Energy Management and Accumulation
Energy Harvesting and Accumulation:
The system monitors the energy harvesting sensor and tracks energy consumption. The energy levels are stored and accumulated over time.
If the energy level is insufficient (based on the energy sensor reading), it could influence decision-making (though this feature is primarily for tracking energy over time).
Decision "Wait for Lift" (Energy-based):
If there is insufficient energy, the elevator may not proceed as expected or could delay operations. However, this is handled more for logging purposes in this system.
6. Random Stop and Destination Floors
Simulated Stops:
The system randomly generates the destination and stop floors to simulate different elevator journeys.
Stop Floors: For each journey, random stop floors are chosen, ensuring that the destination and stop floors are distinct and valid.
Multiple Stops:
The system simulates multiple stops between the start and destination floors, adding a dynamic element to the journey.
The number of stops varies between 1 and 3, and each stop floor is checked to ensure it is valid and not repeating.
7. Data Logging and Output (CSV Format)
Logging Key Data Points:
The system logs and outputs the following data in CSV format:
Timestamp: Time when the data was collected.
Start and End Floors: The start and destination floors for each elevator journey.
Stop Floors: The floors where the elevator stops during the journey.
FSR Value: The weight value from the force sensor.
IR Value: The value from the infrared sensor indicating available space.
Travel Time: The calculated travel time between floors, adjusted for factors such as weight, acceleration, and deceleration.
Energy Level: The energy consumption level during the elevator's operation.
Accumulated Energy: The total energy accumulated over multiple journeys.
Decision: The final decision made based on the conditions (e.g., "Lift Overweight," "Stop at Floor," "Space Unavailable").

