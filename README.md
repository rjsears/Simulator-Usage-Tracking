# Simulator-Usage-Tracking
> Node-Red based simulator time tracking system<br>
> Version 1.0 (2018-10-02)<br>
> Richard J. Sears (richard@sears.net)

This is a node-red based flow that allows you to track simulator (or anything actually) usage based on a list of instructors and selected sim time. Once the instructor and time is selected, the timer starts a countdown. Within a specificed time the system can alert you via pushbullet (free) or SMS (via Twillo (paid)) that the sim session is over or is running late.

Once the session is completed, all of the session information is written to a flat file for storage.


#TODO
Add backend mysql/influs/?? time and session tracking. 
