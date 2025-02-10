# Optimisation_of_LIFTS-TIME_ESTIMATION-USING-IOT

This project tries to optimise the lift by checking whether there are people when the button is pressed and this is constanly checked so that if there is no one the lift wont stop at that floor ,we do this through PIR sensor(Personal infrared sensor) and to determine the time taken for the lift to reach you we have used Ultrasonic sensor and FSR (force sensitive resistor) and in order to see how the lift is optimised we have used Multimeter to monitor the change in energy .The lift time estimation is done through a ml model which keeps a track of all the values in the lift.The whole point of using the ml model is to make the lift provide better more precise time estimation based on the activity of the lift like in certain time stamps the lift might stop more frequently in certain stops.The whole project was done in TinkerCad software feel free to access it from here.

https://www.tinkercad.com/things/eZrI7aOquat-lift-optimisation-and-time-estimation?sharecode=QCOUa4dtwrpbX6FUJhbhBxr7DjjDqprS8yHxc4c4ubE

Here the Time Estimation is calculated through this formula 
    int floorsTravelled = abs(destinationFloor - currentFloor);
    float travelTime = floorsTravelled * baseTravelTimePerFloor * (1 + loadFactor) + accelerationTime + decelerationTime;

As per the project we have tried to adhere to the standards used in the lift industry(SEIS Lift standards)
For further queries please refer the other word document attached 
