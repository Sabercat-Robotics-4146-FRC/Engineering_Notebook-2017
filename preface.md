# Preface
*This documents the vision and motive behind the software written in the 2017 FRC season.*
---
This season, we build our software with principles of good code in mind.

## Robustness
When designing software, its good to keep in mind how a feature might contribute to the program as a whole. When code grows past a certain point in both number of developers and sheer lines of code, better systems for software development are required. At Sabercat Robotics, we use `git` as our verson control software on top of `github` for storing code on a third party server for safe keeping. This ensures that all changes can be reverted if necesary, all engineers have accountability for their work, and the code can't be accidentaly wiped if a computer breaks.

We also use heavy unit testing in order to ensure the software works how intended. Periodically, unit tests can be ran in order to ensure that new changes to the software didn't break anything. Junit provides an easy and light testing enviroment. We made it a goal to use junit heavily in 2017.

Even when evaluating which architecture to build the robot around, we consistantly will make desisions based on how tride and true the method is. For instance, this past offseason, we conducted heavy experimentation with async event loops to run the robot. In the Arizona State Championship, we ran the entire robot on an event loop with a thread pool. We managed to work out the kinks in the design and ultimatly placed second. The problem with the `EventLoop` is not the reliability, its the uncertainty and risk that comes along with running a new software architecture. The `EventLoop` provided simple syntax for defining autonomous, interuptable, processes. I believe that it will be more main stream when the idea moves past user interfaces and server architectures. 

>The problem with the `EventLoop` is not the reliability, its the uncertainty and risk that comes along with running a new software architecture.

Even though the `EventLoop` was a great experiment, it is not proven, yet. With this in mind, we decided to use a more traditional, tried-and-true mehtod of programming. We decided to use Finite State Machines over the `EventLoop`. This decision ultimatly had robustness and acountability in mind. Testing is key; on the state chamionship, our robot was running completely new, untested, code. When errors occurred, the team assumed that the problem was with the new `EventLoop`. Ultamatly, the problem was a hardware issue, damage to the robot radio. The lesson learned was that the lack of trust in the new system led to waisted hours of debugging the robot code when it was no where near the problem.The untested software worked how it was supposed to, *but it won't always do that in the future.*

## Readability

High quality code written for both the computer and the human in front of it. "Self documenting code." does not exist. But, as a developer, its our job to get the closest possible thing to it and then write some killer documentation regaurdless. Thats our job. It makes so much sense to help ourselves out as the programmer. When documentation exists for code, later tweaking jobs will be significantly easier and faster. 
>...as a developer, its our job to get the closest possible thing to [self documenting code] and then write some killer documentation regaurdless.

Because we work in a team of people greater than one, reading other's code is a very important skill. We write code that is easy for others to read, comprehend, and review. Because, if it's not easy to review, it will not be implemented in the official robot code. Peer review is an important aspect of working in a team.


## Utility
 