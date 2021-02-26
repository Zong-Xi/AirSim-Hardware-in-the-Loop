# AirSim Hardware in the Loop (HITL)

---

## Hardware Part

- mRo Pixhawk Flight Controller (pixhawk 1)
- receiver : FrSky TFR8 2.4G
- transmitter : Futaba t10cp

<br>

<table>
    <tr>
        <td><center><img src="https://github.com/Zong-Xi/AirSim-Hardware-in-the-Loop/blob/master/picture/20210220_125103.jpg" ></center></td>
        <td><center><img src="https://github.com/Zong-Xi/AirSim-Hardware-in-the-Loop/blob/master/picture/20210220_125113.jpg" ></center></td>
        <td><center><img src="https://github.com/Zong-Xi/AirSim-Hardware-in-the-Loop/blob/master/picture/20210220_125045.jpg" ></center></td>
    </tr>
    <tr>
        <td><center>pixhawk and receiver</center></td>
        <td><center>transmitter</center></td>
        <td><center>total tools</center></td>
    </tr>
</table>

<br>

## QGroundControl
- Airframe : Quadrotor x s500 Generic
- Safety : Hardware in the Loop Simulation -> HITL enable
  
- Flight Mode : 
  - Manual
  - Altitude
  - Stabilized

<br>

## AirSim 
in `setting.json` :
```json
    {
        "SettingsVersion": 1.2,
        "SimMode": "Multirotor",
        "Vehicles": {
            "PX4": {
                "VehicleType": "PX4Multirotor",
                "UseSerial": true,
                "Parameters": {
                    "NAV_RCL_ACT": 0,
                    "NAV_DLL_ACT": 0,
                    "LPE_LAT": 47.641468,
                    "LPE_LON": -122.140165,
                    "COM_OBL_ACT": 1
                }
            }
        }
    }
```
[px4 setup reference](<https://github.com/Microsoft/AirSim/blob/master/docs/px4_setup.md> =60%)

<br>

## AirSim + QGroundControl + HITL 
- AirSim and Pixhawk connection : using usb port 
    - (in my computer is `serial port:COM6`)
- AirSim and QGC connection : using udp 
    - in Application setting -> Comm Links
    - Listening Port : 14550
    - TargetHosts : 127.0.0.1:14550 (local computer ip) 
    - <img src="https://github.com/Zong-Xi/AirSim-Hardware-in-the-Loop/blob/master/picture/QGC.png" >
    - also need to set the parameter in `AirSim/Setting.json`
    ``` json
    "QgcHostIp": "127.0.0.1", 
    "QgcPort": 14550, 
    ```
- launch QGC -> select udp connection mamually -> launch AirSim 

<BR>

    
## Result
- HITL, using transmitter 
    - [link](<https://youtu.be/jm2-Q2Wo8pk>)

- HITL, using Python code
    - [link](<https://youtu.be/XE08pVrVFdY>)
- HITL + QGC + AirSim, using Python code 
    - [link](<https://youtu.be/i28x2xz901E>)
