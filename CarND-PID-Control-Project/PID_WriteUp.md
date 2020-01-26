# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program
---

## Project Pre-Requisites:
In this C++ project, I use a Proportional-Integral-Derivative Controller, or PID, in order to drive a simulated car around a virtual track. The project involves implementing the controller primarily for steering angle of the car which also simulates the Throttel as well, Achieved this by tuning coefficients for each PID value in order to calculate a steering angle that keeps the car on the track.
### Project Steps
* Implement PID Controller for Steering (optional: controlling throttle as well)
* Optimize init parameters for each PID coefficient

## Results:
A video of the simulated car driving around the track is added in the repo with file name: 

## Working Procedure of PID:

### Closed loop Feedback Controllers:
Any controller which senses its output value and feedbacks to the command the input to follow the desired behaviour is called Closed loop Feedback Controller. PID is one such controller where it uses the error difference between the set point(desired behaviour) and previous output values by the model(system).


The error which will be used in the current Car_Nd project is cross-track error(CTE).
CTE is essentially tells us that how far the car is from the middle line of the road.

There are Primarily three components in PID controller design.
* The "P" for proportional means that the car will steer in proportion to the CTE. Using this information we can tune the controller in the feedback loop. However, if the coefficient is set too high for P, the car will oscillate too much, as the car will constantly overcorrect and overshoot to the middle. If the coefficient is too low, the car may react too slowly to curves when the car gets off-center with a higher CTE.

* The "D" for derivate is the change in CTE from one value to the next. This means that if the derivative is quickly changing, the car will correct itself faster, such as in the case of a curve, and if the car is moving outward from the middle, this will cause the steering to get larger. But if the car is moving towards the center, the car's steering angle will get smoothed out, leading to a more smoother driving experience. D being Too high leads to almost constant steering angle changes of large degrees, where although the car will be well-centered it can hardly move. Too low of a D coefficient will lead to the oscillations being too high with more overshooting.

* The "I" for integral sums up all CTEs up to that point, such that too many negative CTE's will drive up this value, causing the car to turn back toward the middle, preventing the car from driving on one side of the lane the whole time.
If the coefficient is too high for I, the car tends to have quicker oscillations, and does not tend to get up to a quick speed. A low coefficent for I will cause the car to tend to drift to one side of the lane or the other for longer periods of time.

### Finding right coefficients for this project:

Done many manual testings on the tuning part.
Has developed a pythonic version of Twiddle to see the best suited coefficients for the current project.
Which madde me succeed well at the following coefficients: [P,I,D] = (0.2, 0.001, 3.0)

  
