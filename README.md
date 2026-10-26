# Dead Reckoning in Aerial Robotics

Navigation is an important part of aerial robotics. For a drone to travel from one location to another, it needs to estimate its position, direction, and movement. However, GPS or other external positioning systems may not always be available or reliable. Dead reckoning is one method that allows a drone or robot to estimate its position using information about its previous position and subsequent movement.

Dead reckoning is a navigation technique used to estimate the current position of a moving object from a previously known or estimated position, using information such as speed, direction, and elapsed time.

Instead of continuously relying on an external positioning reference, the system calculates how far and in which direction the object has moved, then updates its estimated position.

In aerial robotics, dead reckoning can use measurements from onboard sensors, including accelerometers and gyroscopes in an Inertial Measurement Unit (IMU). Depending on the navigation system, heading and velocity measurements may also be used.

## How Dead Reckoning Works

Dead reckoning follows a series of steps:

1. **Establish a starting position:** The drone begins with a known or estimated position.
2. **Measure movement:** Sensors or navigation instruments provide information about movement, speed, acceleration, or direction.
3. **Calculate displacement:** The system estimates how far the drone has moved during a time interval.
4. **Update the position:** The calculated displacement is added to the previous position estimate.
5. **Repeat the process:** The estimate is continuously updated as the drone moves.

For example, if a drone's estimated position is 10 metres east of its starting point and it then travels another 5 metres east, its new estimated position is 15 metres east of the starting point.

A simplified relationship is:

**New estimated position = Previous estimated position + Estimated displacement**

For movement at a known constant speed in a straight line:

**Distance travelled = Speed × Time**

When direction is included, the displacement can be resolved into components along the coordinate axes. Real drone navigation is more complex because the aircraft moves in three dimensions and its orientation changes during flight.

## Example in Aerial Robotics

Consider a drone that starts at a known position and moves horizontally at an estimated speed of 2 metres per second for 5 seconds.

The estimated distance travelled is:

Distance = Speed × Time

Distance = 2 × 5 = 10 metres

If the drone travels directly east and its starting position is represented by coordinates (0, 0), its estimated final position is (10, 0) metres.

If it subsequently travels 3 metres north, its estimated position becomes (10, 3) metres.

This example assumes that the speed and direction measurements are accurate and that the drone follows the intended path. In practice, wind, sensor noise, and changes in heading can make the actual position different from the estimate.

## Applications of Dead Reckoning

### Drone navigation

Dead reckoning can help drones estimate their movement between external position updates. This is useful when GPS signals are weak, interrupted, or unavailable.

### Autonomous mobile robots

Ground robots can estimate their movement using wheel encoders, inertial sensors, or other onboard measurements. These estimates help them navigate between locations.

### Underwater vehicles

Underwater vehicles may have limited access to GPS because satellite signals do not propagate effectively through water. They can use inertial sensors and other navigation instruments to estimate their position while submerged.

### Aircraft navigation

Aircraft can estimate their position between navigation fixes using heading, speed, elapsed time, and other motion measurements.

### Indoor navigation

Robots operating inside buildings, warehouses, or other GPS-denied environments can use dead reckoning as part of their localisation systems.

## Limitations of Dead Reckoning

Despite its usefulness, dead reckoning has several limitations.

### Accumulation of errors

Small errors in speed, direction, or sensor measurements accumulate as the system repeatedly updates its position. As a result, the estimated position can gradually drift away from the actual position.

### Sensor noise and bias

Accelerometers and gyroscopes are not perfectly accurate. Noise and small measurement biases can affect velocity, orientation, and position estimates.

### Dependence on the starting position

Dead reckoning updates a previous position estimate. If the initial position is incorrect, subsequent estimates may also be incorrect.

### Environmental disturbances

Wind can push a drone away from its intended path. If the navigation system does not adequately account for this movement, its estimated position may differ from the drone's actual position.

### Limited long-term accuracy

Because errors accumulate over time, dead reckoning alone may become unreliable for long journeys. Periodic corrections from GPS, visual landmarks, cameras, or other external references can improve the overall navigation estimate.

## Improving Dead Reckoning Accuracy

Dead reckoning is often combined with other navigation methods rather than used entirely on its own.

- **GPS/GNSS:** Provides external position estimates when satellite signals are available.
- **Sensor fusion:** Combines information from different sensors to produce a more reliable estimate.
- **Visual odometry:** Estimates movement by analysing changes between images captured by a camera.
- **Landmark-based localisation:** Uses recognisable features in the environment to correct position estimates.
- **Calibration:** Helps reduce errors caused by inaccurate sensor measurements.

For example, an aerial robot may use an IMU to track rapid changes in movement and combine those measurements with GPS updates to limit long-term position drift.

## Summary

Dead reckoning is a navigation method that estimates a moving object's current position from a previous position and information about its movement. In aerial robotics, it can help drones estimate their positions using onboard motion sensors and other navigation measurements, including during periods when external positioning information is unavailable.

Its main advantage is that it can provide continuous position estimates without requiring a constant external position fix. However, measurement errors accumulate over time, reducing accuracy. For this reason, practical robotic navigation systems often combine dead reckoning with GPS, visual information, or other sensors to improve reliability.

## Sources

1. **Smithsonian National Air and Space Museum, Time and Navigation:** *Dead Reckoning: An Educated Guess.*  
   https://timeandnavigation.si.edu/navigating-air/challenges/overcoming-challenges/dead-reckoning

2. **IEEE Technology Navigator:** *Dead Reckoning.*  
   https://technav.ieee.org/topic/dead-reckoning/

3. **NASA Technical Reports Server:** *A Short Tutorial on Inertial Navigation System and Global Positioning System Integration.*  
   https://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/20150018921.pdf

4. **Technical University of Munich, Institute of Flight System Dynamics:** *Inertial Navigation.*  
   https://www.fsd.ed.tum.de/research/sensors-data-fusion-and-navigation/research-and-competence-areas/inertial-navigation/

These sources provide background on dead reckoning, its role in navigation, inertial sensor systems, and the accumulation of positioning errors.
