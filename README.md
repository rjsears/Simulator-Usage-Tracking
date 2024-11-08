# Simulator-Usage-Tracking
> Node-Red based simulator time tracking system<br>
> Version 1.0 (2018-10-02)<br>
> Richard J. Sears (richardjsears@gmail.com)

This is a node-red based flow that allows you to track simulator (or anything actually) usage based on a list of instructors and selected sim time. Once the instructor and time is selected, the timer starts a countdown. Within a specificed time the system can alert you via pushbullet (free) or SMS (via Twillo (paid)) that the sim session is over or is running late. Includes the ability to pause the session for a break or a maintenance issue without affecting the remaining simulator time available. 

Once the session is completed, all of the session information is written to a flat file for storage.<br>

# Installation
- Download and install steelseries gauges
- Copy the JSON flow to your clipboard and then import into Node-RED using the <i>Import From > Clipboard</i> (Ctrl-I) menu option
- Make necessry changes for steelseries directory locations
- Make necessry changes to your log file locations in the "Session Log File" nodes. Currently ~root/.node-red
<br>

# Requirements
The only real requirement is the steelseries gauges by Gerrit Grunwald & Mark Crossley. If you want notifications, then you will also need the PushBullet or Twillio Node-Red nodes. <br>
For the steelseries gaugues, download them and untar them at a location that your node-red can access (typically ~user/.node-red/static) and then point to that directory in your widgets. For example this is the js for the "Sim Gauge Tech View" gauge: <br>

```js
<script src="/myjs/steelseries/tween-min.js"></script>
<script src="/myjs/steelseries/steelseries-min.js"></script>
<script>
var radial4;
    (function(scope){ 
        scope.$watch('msg', function(msg) {
           if (typeof(msg.value) != "undefined") radial4.setValueAnimated(msg.value);
           if (typeof(msg.threshold) != "undefined") radial4.setThreshold(msg.threshold);
           if (typeof(msg.maxvalue) != "undefined")radial4.setMaxValue(msg.maxvalue);
           if (typeof(msg.userLed) != "undefined") radial4.setUserLedOnOff(msg.userLed);
        });
    })(scope);

    var sections = [steelseries.Section(-40, 5, 'rgba(220, 0, 0, 0.3)'),
                        steelseries.Section(5, 10, 'rgba(255, 255, 0, 0.5)'),
                        steelseries.Section(10, 240, 'rgba(0, 255, 0, 0.3)') ],

            // Define one area
    areas = [steelseries.Section(-40, 5, 'rgba(220, 0, 0, 0.3)')],

    radial4 = new steelseries.Radial('canvasRadial4', {
            gaugeType: steelseries.GaugeType.TYPE4,
            size: 292,
            section: sections,
            //MaxValue: 240,
            area: areas,
            lcdDecimals: 0,
            minValue: -30,
            titleString: "Sim Time Remaining",
            unitString: "Minutes",
            threshold: 10,
            thresholdRising: false,
            userLedVisible: true,
            userLed: true,
            useOdometer: false,
            lcdVisible: true,
            trendVisible: false,
        });
                        
    radial4.setFrameDesign(steelseries.FrameDesign.BLACK_METAL);
    radial4.setBackgroundColor(steelseries.BackgroundColor.LIGHT_GRAY);
    radial4.setValueAnimated(0);
    radial4.setThreshold(10);
    radial4.blinkUserLed(0);

</script>

<canvas id="canvasRadial4" width="401" height="401"></canvas>
```
<br>
# Screen Shots

![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_node-red.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_main_interface.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_time_instructor_select.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_time_time_select.png?raw=true)<br>
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/sim_tracking_main_interface_running.png?raw=true)<br>

<br><br>

# In Use
We use a small 7" touchscreen powered by a Raspberry Pi to run the system:
![alt tag](https://github.com/rjsears/Simulator-Usage-Tracking/blob/master/images/raspberry_pi_touchscreen.png?raw=true)<br>



## TODO
* Add MySQL backen to track usage
* Add E-Mail reporting

## Authors

* **Richard J. Sears** - *richardjsears@gmail.com* - [The RS Technical Group, Inc.](http://github.com/rjsears)

## License

This project is licensed under the MIT License - see the MIT License for details

## Acknowledgments

* [Gerrit Grunwald, Mark Crossley](https://github.com/HanSolo/SteelSeries-Canvas) - Steel Series Gauges
* Node-RED Google Group for all the help with my questions!
* My amazing family that puts up with all of my coding projects!
