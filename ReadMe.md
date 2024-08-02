# NTRIP Client

ROS 2 package for publishing RTCM correction data from an NTRIP server.

### Publishers

|Topic | Type | Description  |
|---------|---------|---------|
| `/rtcm` | [`rtcm_msgs/msg/Message`](https://github.com/tilk/rtcm_msgs/blob/master/msg/Message.msg) | RTCM Correction data |


### Parameters
|Parameter | Type  |   Values  | Runtime R/W | Description  |
|---------|---------|---------|---------|---------|
| `use_https` | bool |  `true/false` | `read-only` | HTTPS will be used if set true. | 
| `host` | string |   | `read-only` | NTRIP sever hostname |
| `port` | string | `2101/2102`| `read-only`  | NTRIP server port |
| `mountpoint` | string |  |  `read-only`|  Mountpoint to connect |
| `username` | string |  | `read-only` | Login credentials for the NTRIP subscription  |
| `password` | string |  | `read-only` | Login credentials for the NTRIP subscription  |


## RTK Correction Services

RTK (Real-Time Kinematic) correction service is a technique used to enhance the precision of position data derived from satellite-based positioning systems such as GPS, GLONASS, Galileo, and BeiDou. RTK achieves centimeter-level accuracy by using corrections transmitted from a network of ground-based reference stations to a receiver in real time. 

Here is a free RTK correction service that you can use with the NTRIP client.

### RTK2go

RTK2go is a community NTRIP Caster that provides RTK correction service for free. To use it, select a mountpoint near your location. You can find the list of available mountpoints [here](http://monitor.use-snip.com/map). Click on **`view-all`** to view mountpoints on the map.

Once you have the mountpoint you would like to connect to, add that to the config file as shown below.


```yml
ntrip_client:
  ros__parameters:
    use_https: false
    host: rtk2go.com
    port: 2101
    mountpoint: Prittlbach  # Add your mointpoint here
    username: "noname"
    password: "password"
```
