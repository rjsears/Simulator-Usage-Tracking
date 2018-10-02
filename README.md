# Simulator-Usage-Tracking
> Node-Red based simulator time tracking system<br>
> Version 1.0 (2018-10-02)<br>
> Richard J. Sears (richard@sears.net)

This is a node-red based flow that allows you to track simulator (or anything actually) usage based on a list of instructors and selected sim time. Once the instructor and time is selected, the timer starts a countdown. Within a specificed time the system can alert you via pushbullet (free) or SMS (via Twillo (paid)) that the sim session is over or is running late.

Once the session is completed, all of the session information is written to a flat file for storage.<br><br>

![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_node-red.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_main_interface.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_time_instructor_select.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_time_time_select.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_main_interface_running.png?raw=true)<br>



#TODO
Add backend mysql/influs/?? time and session tracking. 
