WattMote
--------------

Source files for WattMote - [a wireless KillAWatt mod similar to the TweetAWatt](http://lowpowerlab.com/blog/2012/12/20/tweet-a-watt-alternative-solution/)
See LowPowerLab for more details, schematic, assembly programming.


[Moteinos](http://lowpowerlab.com/blog/2012/12/20/moteino-the-wireless-low-power-low-cost-arduino-clone/) are used 
to receive data from remote WattMotes. These WattMotes run 
[the WattMote.ino sketch](https://github.com/LowPowerLab/WattMote/blob/master/WattMote.ino).
<br/>On the receiving end there is a Moteino that simply passes the incomming data through to the serial port.
This data is then parsed by the WattMote.py script provided in this repository.
<br/><br/>
The receiver Moteino should be running a simple [Moteino serial-passthrough sketch](https://github.com/LowPowerLab/RFM12B/blob/master/Examples/Receive/Receive.ino).
This will pass any incoming data to the Python script that will parse it and submit it to EmonCMS for storage.
<br/>See [this post](http://lowpowerlab.com/blog/2012/12/28/wattmote-motei…less-killawatt/) for details on how to setup your RaspberryPi to receive serial data from the receiving Moteino.

####Command line options for WattMote.py:

     -d               Set DEBUG=True
     -g               Set GRAPH=True (requires these python libs: wx, numpy, matplotlib, pylab)
     -s SPort         Read from serial port SPort (Default:  /dev/ttyAMA0 )
     -b Baud          Set serial port bit rate to Baud (Default:  115200 )
     -emonhost HOST   Set EMONHost to HOST (Default:  localhost )
     -emonkey  KEY    Set EMONAPIKey to KEY
     -emonport PORT   Set EMONHostPort to PORT (Default:  80 )
     -h               Print this message
