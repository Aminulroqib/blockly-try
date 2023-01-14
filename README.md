# Otto Blockly Web
Otto Blockly Web version

## Agent communication

To enable communication between ottoschool.com (https://ottoschool.com/blockly) and the [Arduino Create Agent](https://github.com/arduino/arduino-create-agent)
add `origins = http://ottoschool.com` on your agent config.ini file
(if you are using https, add `origins = https://ottoschool.com`).

- On macOs ~/Applications/ArduinoCreateAgent/ArduinoCreateAgent.app/Contents/MacOS/config.ini
- On Linux ~/ArduinoCreateAgent/config.ini
- On Windows C:\Users\\[your user]\AppData\Roaming\ArduinoCreateAgent

### Sample config.ini

```
# Type of garbage collection. std = Normal garbage collection allowing system to decide 
# (this has been known to cause a stop the world in the middle of a CNC job which can 
# cause lost responses from the CNC controller and thus stalled jobs. use max instead to
# solve.), off = let memory grow unbounded (you have to send in the gc command manually
# to garbage collect or you will run out of RAM eventually), max = Force garbage collection
# on each recv or send on a serial port (this minimizes stop the world events and thus
# lost serial responses, but increases CPU usage)
gc = std
# Override the hostname we get from the OS
hostname = unknown-hostname  
# Regular expression to filter serial port list
regex = usb|acm|com  
# show debug logging
v = true  
appName = CreateAgent/Stable
updateUrl = https://downloads.arduino.cc/
origins = https://ottoschool.com, https://local.arduino.cc:8000
#httpProxy = http://your.proxy:port # Proxy server for HTTP requests
crashreport = false # enable crashreport logging
```
