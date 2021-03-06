# Modular Syringe Driver
Welcome to the Modular Syringe Driver repository! Here, you will find all the necessary information to create your own version of this device.

Here is the finished product:

![Alt img](https://cloud.githubusercontent.com/assets/13821621/21351274/a834174a-c6b3-11e6-9b17-f11d35228eb4.png)

All designs are hosted on Onshape:
* [Syringe Driver](https://cad.onshape.com/documents/56ab4447e4b0dff6d869c7ac/w/10403a3c4431f66501924e81/e/ad868b310df8ef7bb56f2516)
* [Modularity](https://cad.onshape.com/documents/20421eb13def16ddb65f3155/w/9ed7d19760b1ecfa0f48b9ff/e/2a6517c7e659cf206dda40c0)

For a list of all the materials you will need, please see the [Materials](hardware/materials.md) documentation.
* Note: A 3D printer is required to obtain some of these materials.

## Modularity
The appeal of this device is its modularity. Many different additions can be designed and printed for this device.
Here are a few examples of possible additions:

![Alt text](https://cloud.githubusercontent.com/assets/13821621/21388125/cb2ab0be-c772-11e6-8bb6-918225a8d813.png)

## Dependencies
* [Commanduino](https://github.com/croningp/commanduino)
* [Arduino CommandHandler](https://github.com/croningp/Arduino-CommandHandler)
* [Arduino CommandTools](https://github.com/croningp/Arduino-CommandTools)

## Assembly
Please see the the [Assembly](hardware/assembly.md) documentation for information on assembly.

## Example Usage
Below is an example of how to use [commanduino](https://github.com/croningp/commanduino) to communicate with the syringe driver.
Here we import the CommandManager which is used to communicate with the hardware via Arduino.
We also import the Axis device from Commanduino which allows the syringe to be placed on an XY axis for independent movement.

Variables are set up for the individual components of the driver, such as how many mm/step the motor should move, and the maximum volume of the syringe etc.
Instantiating an Axis object with the stepper information and passing it to the Syringe allows us full access to the Syringe commands.

See the [Syringe software](software/syringe.py) for more information on the syringe commands. 

JSON Example for setting up the Linear Accelerator Actuator in commanduino:
```json

{
  "ios" : [
    {
      "port": "/dev/tty.usbmodem1411"
    },
    {
      "port": "/dev/ttyACM0"
    },
    {
      "port": "/dev/ttyACM1"
    },
    {
      "port": "/dev/ttyACM2"
    }
  ],
  "devices": {
    "stepper": {
      "command_id": "LS1",
      "config": {
        "enabled_acceleration": false,
        "speed": 1000,
        "max_speed": 1000,
        "acceleration": 1000
      }
    }
  }
}
```

Python code for setting up the Syringe Driver: 

``` python
from commanduino import CommandManager
from commanduino.devices.axis import Axis
from syringe import Syringe

configfile = os.path.join(HERE_PATH, 'robot_config.json')
cmdMng = CommandManager.from_configfile(configfile)

MICROSTEP = 32.0
LINEAR_STEPPER_UNIT_PER_STEP = 0.05  # mm/step
SYRINGE_UNIT_PER_MM = 250 / 59.70  # 59.70mm for 250ul
SYRINGE_MAX = 235
SYRINGE_AXIS = Axis(cmdMng.S1, LINEAR_STEPPER_UNIT_PER_STEP * SYRINGUE_UNIT_PER_MM / MICROSTEP, 0, SYRINGE_MAX)
SYRINGE = Syringe(SYRINGE_AXIS, SYRINGE_MAX)
```

## Authors

Design and code by [Jonathan Grizou](http://www.chem.gla.ac.uk/cronin/members/Jonathan/), documentation by [Graham Keenan](https://github.com/ShinRa26), while working in the [Cronin Group](http://www.chem.gla.ac.uk/cronin/).

## Licenses

|   License     |     Hardware    |   Software      |
| ------------- | :-------------: | :-------------: |
| Title  | [Creatives Commons BY-SA](http://creativecommons.org/licenses/by-sa/4.0/)  |[GPL v3](http://www.gnu.org/licenses/gpl.html)  |
| Logo  | [![Creative Commons BY-SA](https://i.creativecommons.org/l/by-sa/4.0/88x31.png) ](http://creativecommons.org/licenses/by-sa/4.0/)  |[![GPL V3](https://www.gnu.org/graphics/gplv3-88x31.png)](http://www.gnu.org/licenses/gpl.html)  |
