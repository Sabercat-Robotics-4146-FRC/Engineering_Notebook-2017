# PID Loops in Java
----
When designing a general purpose pid loop system, we intended to write industrial class loops that midigate common novice problems like integral windup and jaggy behavior. Although we don't use embedded systems for PID controllers, we've optimized our code to be as precise as possible.

## PID Basics

Our PID class has all combinations of contollers availible. (ie PI, PD controllers)

## Iterative Implementation

### Proportional Control

### Derivative Control


### Integreal Control

When sampling the Integral of the system error, we have to use a discrete riemann sum. This is accomplished by taking the error and multiplying it by clock cycle time. This value is then added to the integral accumulator. Because the accumulator would wind up and provide odd behavior, we actually use an abstraction data type called a "SizedStack" to calculate the integral. The SizedStack is just an array that has a set size, when a value is added to it, and its at capacity, it drops the oldest value. This allows us to store the values of the integral over a given iterative interval. So we can have the integral term only take the last n iterations, where n is the number of iterations the integral should take into account. The interval size needs to be set before sampling starts because our code is memory efficient and only stores the number of iterations specified at most. The SizedStack also has a bunch of methods for taking the mean, sum, and standard deviation of the data. 

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2a/Riemann_sum_convergence.png/300px-Riemann_sum_convergence.png">

The higher the sampling rate, the more precise the Integral value will be.

## Cascading PID 

Although we don't have a use for the added complexity that cascading PIDs provide, the code we use has the capability. 

## Our Applications in PID
