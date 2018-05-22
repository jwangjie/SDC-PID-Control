# PID Control

Two PID controllers for steering and throttle in C++ to maneuver the vehicle around the track in a simulator were developed. The input is the cross track error (CTE) measured in the simulator, the outputs are the steering and throttle commands. 

## My simulation result:
[![My simulation video](https://github.com/jwangjie/SDC-PID-Control/blob/master/PID.png)](https://youtu.be/UWmtsb8blMk)

## P, I, D regulator

A detailed description of PID controller can be found [PID Controller.pdf](https://github.com/jwangjie/SDC-PID-Control/blob/master/PID%20Controller.pdf). Here is a brief description of the individual effect of the P, I, D regulator.

* Proportional gain: contribute to but not guarantee stability, directly correct the CTE, medium rate responsiveness. 
* Derivative gain: an anticipatory regulator, measuring current and anticipating incoming errors and conduct correction before large errors arrive, should NEVER be used alone.   
* Integral gain: a looking back regulator, summing past errors and then respond, slow rate responsiveness, normally small. 

## Hyperparameters 

The gains of the PID controller were determined by trial and error method. There are two general rules to guide the process:
* Pick positive values for P, I, and D gains to make sure the system will remain stable 
* Set the integral gain to zero and pick the P and D gains as if designing a PD controller. Then go back and pick sort of an I gain.

The integral gain is relatively small compared to PD gains. For a simple task such as the throttle control, a PD controller is enough. 

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 

