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
[px4 setup reference](<https://github.com/Microsoft/AirSim/blob/master/docs/px4_setup.md>)

<br>

## Result
- https://youtu.be/jm2-Q2Wo8pk
- [![HITL Test](https://github.com/Zong-Xi/AirSim-Hardware-in-the-Loop/blob/master/picture/block.png)](https://youtu.be/jm2-Q2Wo8pk)
