#Technical Documentation: Mechanical Design

## *Strategy*
[TODO: fill out strategy]

## *Design Goals and Principles*
[TODO: fill out design goals/principles]

## *Drivetrain Design*
The drive train was built for versatility, robustness, and modularity. Design was heavily influenced by our manufacturing capabilities. Our primary manufacturing facility has tooling for sheet metal, so we designed most of the robot, including the drivetrain, in sheet metal. The decision was reinforced by the sheet metal design tools provided by Solidworks. We used 6061-T6 alloy 0.0625” sheets for a majority of parts.
### Drive Wheels
We chose to use 8” OD pneumatic wheels for our robot this year. The wheels allow us to regulate the speed and traction by setting the pressure of the wheels. 

[TODO: Insert tire presure image comparison]

We used these wheels for their high traction. This will provide a higher grip when being defended against. A six (6) wheel skid drive train is used; three (3) wheels on each side of the drivetrain. These wheels are belted together using HTD 15mm belts. Although belts are more prone to slipping, they are lighter than chain and gears. The weight of the wheels was a concern; all six (6) drive wheels weigh approximately 10.8 lbs. The wheels alone would be nine percent (9%) of the total robot weight, assuming a 120lb robot.

### Drive Power and Reduction

In the 2017 season, speed and agression is a must have for a drive train. The game is less about what can be accomplished and more about how efficient the task is accomplished. When designing the drive train, the motor power and reduction is one of the most important features of the drive train. The dirve power determines the speed of the robot, which is directly proportional to scoring rates, and how much your robot can push and avoid pushing. Pushing is most important in finals. When the motor is geared for torque over speed, the robot will be more consistant because it cannot be blocked as easily. This defense feature in tandom with high traction wheels make a robot that is harder to defend, which is a very good feature for the finals. In the beginning of the gearbox design, we were considering the possibility of the *"two and a half cim"* drive train, where each side of the skid drive is driven by two cims and a minicim. This would provide us an edge in the speed category. We were looking for a single-speed-single-reduction (SSSR) gearbox. The best fit for our needs was on the VEX Pro store.

<center><img src="./images/SSSR.jpg"></center>

The issue came when the highest reduction the gearbox supported was a 7:1. We did the math against the Tough-box mini's which we used in pervious years. If we were to use the 7:1 SSSR gearbox, we would loose seven pounds (7lbs) of pushing power, and only increase our speed by 30% in a perfect world. This was an unacceptable loss of torque. The SSSR would be havier and harder to do finely controlled programming for. Because of this, and the overall cost of ordering four (4) new gearboxes for both the robot, and the practice robot, we decided to go with the Tough Box Mini's. The mini's are a tride and true gearbox with built in encoders and we had enough in supply for both robots. 

<center><img src="./images/Tough Box.jpg"></center>

### Fasteners

This year's fastener choice was heavily influenced by that of previous years with a few tweaks. We made the desicion to have less hardware diversity. This means that we are less likely to not have the correct size of something in case of breaking. For instance, last year, our climber was had a hook which was fastened to an arm with one 1" countersunk #10 made of special hardeded steel to be able to take the load. in competition, the load from the 120lb robot made the screw very dificult to repair when it came arround to routine arm maintenance. The screw was stripped due to someone useing a very small #2. When it came to needing a new screw, we didn't have any extra because of how specific the screw was, and no other teams around us has any. This made it very dificult to repair the arm while using a stripped screw. This year, we are using generic #10 screws almost exclusivly. This means that we can just bring a surplus of generic screws and we will never have any problems with specialized hardware breaking. Instead of ungodly ammounts of nylock nuts we used in previous years, we are increasing the frequency of rivnut on the robot. The use of rivnuts makes removing and attatching modules from the robot quicker because the nut doesn't need to be heald in place in order to unscew a fastener. One of the reasons that rivnuts were not used as frequently last year is due to their easy stip torque. In previous years, we used aluminum rivnuts, but by using a mix of aluminum and steel this year, we can have fasteners that support over tightened screwes.

# Manufacturing and Fabrication

<span style="color: red;">
*When Manufacturing, safety is our top priority. Propper PPE are training are of the upmost importance.*
</span>

## Sheet Metal Cuts

Our team manufactures most of the parts by hand. We use 1:1 drawings made by our design team in Solidworks. The manufacturing process beigns with the design team, they must develop a cutlist and drawing list with the correct number of parts that need to be manufactured. We then print out the 1:1 drawings, and cut the sheet metal to bounding rectangles of the size. 