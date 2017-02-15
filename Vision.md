# Documentation: Vision

## *Meet the Pixy*
This year we are using the [pixy camera from charmed labs](http://charmedlabs.com/default/pixy-cmucam5/ "Pixy (CMUcam5) | Charmed Labs") to complete the much needed, yet difficult, task of equipting our robot with vision capabilities to find what it's looking for.<img src="./images/Terminator.jpg"> 

### *Why the Pixy?*

Over the 2016-2017 offseason, our programming team worked on a vision system that would be robust, reusable, and fast. This was acomplished by a [Raspberry Pi](https://www.raspberrypi.org/) coprocessor overclocked, running some OpenCv code written in Python. The program had a desktop interface in GTK written so that our team could tweak the vision HSV filter parameters anywhere with a laptop and a camera; we wouldn't need to have the robot on the field in order to tweak its vision. A file would be generated from the laptop and transfered to the pi. The pi would end up doing most of the number crunching, and transfering the width, height, and x and y coordinates to the roborio, via NetworkTables. The pi would run a very light weight distribution of Arch Linux becuase it has better camera driver support. More information about our 2016 intermediate season code can be found [here.](https://github.com/Sabercat-Robotics-4146-FRC/Vision_Processing-2016)

So, why did we choose the Pixy over our own working vision code that we developed ourselves? The determining factor was speed: the Pixy has a higher update frequecy over our Raspberry pi coprocessor. Although the pi has more memory and processing power, the fact that it has to run an operating system on top of the OpenCv code makes it slower. The integrated nature of the Pixy makes it faster. Although we considered using a Nvidia Jetson TX1 to run our OpenCv vision code, we decided against it based on its sheer size and power consumption.
 
### *About the Pixy*

The Pixy is an integrated computer-camera which will do all of the vision processing locally and then only transfer the data we need to the roborio. This provides a low bandwidth, high frame-rate solution to vision processing. The pixy is sporting a 1280x800 resolution camera, but only will run vision processing at 320x200 due to memory restraints on the Pixy. This lower resolution provides a 50Hz refresh rate. There is a mode where 25Hz is supported with full resolution, but for our applications, the lower resolution and higher update frequency is more favorable. This tradeoff is a direct result of the lower (264Kb) memory capacity of the Pixy.

- Processor: NXP LPC4330, 204 MHz, dual core
- Image sensor: Omnivision OV9715, 1/4", 1280 x 800
- Lens field-of-view: 75 degrees horizontal, 47 degrees vertical
- Lens type: standard M12 (several different types available)
- Power consumption: 140 mA typical
- Power input: USB input (5V) or unregulated input (6V to 10V)
- RAM: 264K bytes
- Flash: 1M bytes
- Available data outputs: UART serial, SPI, I2C, USB, digital, analog
- Dimensions: 2.1" x 2.0" x 1.4
- Weight: 27 grams

<center><img src="./images/Pixy.jpg"></center>

The Pixy allows us to track multiple targets based on color signatures. The pixy relays five very useful pieces of information for each block. The pixy uses classical HSV image filtering to calculate bounding boxes around each object. It tells us what *type* of block we are detecting. This allows us to determine what object the sensor is detecting. The Pixy will also give us the bounding box center *x* and *y* coordinates of the object relative to the camera. The origin of the camera is in the top left of the image with both x and y increasing to the lower right. The final information that the Pixy provides is the width and height of the object. This lets us determine approximate distances and such from the area information.

### *Communicating with the roboRIO*

Initially we had planned on directly communicating with the ROBORio through it's SPI port by creating our own cable capable of transfering data between the pixy and roborio. It was wired as follows:

<center><img src="./images/roboRIO-to-Pixy SPI connection configuration.jpg"></center>

However, as we looked more and more into the specifics of programming using the pixy over SPI, we decided it would be best to instead use the USB feature of the pixy and are now interfacing it a Raspberry Pi using the libpixyusb library supplied from charmed labs. From the Pi we then are putting the pixy values into a network table to get them to the ROBORio.
