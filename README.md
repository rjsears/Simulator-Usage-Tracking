# Simulator-Usage-Tracking
> Node-Red based simulator time tracking system<br>
> Version 1.0 (2018-10-02)<br>
> Richard J. Sears (richard@sears.net)

This is a node-red based flow that allows you to track simulator (or anything actually) usage based on a list of instructors and selected sim time. Once the instructor and time is selected, the timer starts a countdown. Within a specificed time the system can alert you via pushbullet (free) or SMS (via Twillo (paid)) that the sim session is over or is running late.

Once the session is completed, all of the session information is written to a flat file for storage.<br>

# Installation
To install, simply open your node-red interface and import the json file. Make necessary changes

# Requirements
The only real requirement is the steelseries gauges by Gerrit Grunwald & Mark Crossley. If you want notifications, then you will also need the PushBullet or Twillio Node-Red nodes. <br>
For the steelseries gaugues, download them and untar them at a location that your node-red can access (typically ~user/.node-red/static) and then point to that directory in your widgets:<br>

- <script src="/myjs/steelseries/tween-min.js"></script>
- <script src="/myjs/steelseries/steelseries-min.js"></script>

# Screen Shots

![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_node-red.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_main_interface.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_time_instructor_select.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_time_time_select.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_main_interface_running.png?raw=true)<br>

<br><br>


## TODO
* Add MySQL backen to track usage
* Add E-Mail reporting

## Authors

* **Richard J. Sears** - *richard@sears.net* - [The RS Technical Group, Inc.](http://github.com/rjsears)

## License

This project is licensed under the MIT License - see the MIT License for details

## Acknowledgments

* [Gerrit Grunwald, Mark Crossley](https://github.com/HanSolo/SteelSeries-Canvas) - Steel Series Gauges
* My amazing family that puts up with all of my coding projects!
