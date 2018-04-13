# Input
Input bindings are configured through the JSON configuration file named "config.json". 
## Format
The format used is as such:
```
{
  control_type: {
    "bindings": {
      action_name: [binding_alias_1, binding_alias_2, ...]
    },
    "sensitivity": {
      binding_alias: sensitivity_value
    },
    "dead_zone": {
      binding_alias: dead_zone_value
    }
  }
}
```
An example config JSON:
```
{
  "mouse": {
    "sensitivity": 3.00,
    "bindings": {
      "look_analogue": ["mouse_move"]
    }
  },
  "keyboard": {
    "bindings": {
      "jump": ["Space", "Backspace"],
      "forward": ["W", "Up"],
      "back": ["S", "Down"],
      "left": ["A", "Left"],
      "right": ["D", "Right"]
    }
  },
  "controller": {
    "bindings": {
      "jump": ["button_a"],
      "move_analogue": ["stick_left"],
      "look_analogue": ["stick_right"],
      "fire_pimary": ["trigger_right"],
      "fire_secondary": ["trigger_left"]
    },
    "sensitivity": {
      "stick_left": 1.0,
      "stick_right": 0.05
    },
    "dead_zone": {
      "stick_left": 0.4,
      "stick_right": 0.4,
      "trigger_left": 0.3,
      "trigger_right": 0.3
    }
  }
}
```
## Actions 
| Action Name | Alias |
| --- | --- |
| Jump | `jump` |
| Primary fire | `fire_pimary` |
| Secondary fire | `fire_secondary` |
| Analogue movement | `move_analogue` |
| Analogue look | `look_analogue` |
| Move forward | `forward` |
| Move back | `back` |
| Move left | `left` |
| Move right | `right` |
| Pause | `pause` |
| Quit | `quit` |
| Start | `start` |
## Binding Aliases
Keyboard bindings are done using the built in SDL functions. A reference can be found here. The rest have Aliases defined below.

| Mouse Binding Name | Alias |
| --- | --- |
| Mouse Movement | `mouse_move` |
| ~ | ~ |
| Left mouse button | `mouse_button_left` |
| Middle mouse button | `mouse_button_middle` |
| Right mouse button | `mouse_button_right` |
| Auxiliary mouse button 1 | `mouse_button_aux_1` |
| Auxiliary mouse button 2 | `mouse_button_aux_2` |
| Auxiliary mouse button 3 | `mouse_button_aux_3` |
| Auxiliary mouse button 4 | `mouse_button_aux_4` |
| Auxiliary mouse button 5 | `mouse_button_aux_5` |
| Auxiliary mouse button 6 | `mouse_button_aux_6` |

| Controller Binding Name | Alias |
| --- | --- |
| A button | `button_a` |
| B button | `button_b` |
| X button | `button_x` |
| Y button | `button_y` |
| Back button | `button_back` |
| Guide button | `button_guide` |
| Start button | `button_start` |
| Left stick | `left_stick` |
| Right stick | `right_stick` |
| Left shoulder | `left_shoulder` |
| Right shoulder | `right_shoulder` |
| D-pad up | `dpad_up` |
| D-pad down | `dpad_down` |
| D-pad left | `dpad_left` |
| D-pad right | `dpad_right` |
| ~ | ~ |
| Left stick | `stick_left` |
| Right stick | `stick_right` |
| ~ | ~ |
| Left trigger | `trigger_left` |
| Right trigger | `trigger_right` |

## Default Bindings
For some actions, if no binding is provided, then a default will automatically be assigned by the engine. These actions and their corresponding default actions are listed below.

| Action | Binding |
| --- | --- |
| Analogue look | Mouse movement |
| Move forward | W |
| Move back | S |
| Move left | A |
| Move right | D |
| Jump | Space |
| Primary fire | Left mouse |
| Secondary fire | Right mouse |
| Pause | Escape |
| Quit | Q |
| Start game | Return |

## Channels
Input is handled through channels which are essentially a container for a value, updated frequently, this value could be a vector, a float or a boolean. When the channel changes it notifies its listeners. The channel base class has parameters which is uses to filter input so listeners are not notified unnecessarily. These filters include:
- dead zone / activation point
- also sensitivity
- auto-zero
- always notify listener
- bound
#### Dead Zone / Activation Point
If an analogue input (ex. analogue stick, mouse movement) is set to an analogue action (ex. movement) then it functions a threshold, i.e. if the value for an input is lower than that the dead zone value it is set to zero, if it greater than the dead zone it is unchanged. If an analogue input is set to a digital action (ex. jump) then the dead zone functions as an activation point, i.e. if the input value is less than the dead zone then the input is 'off', if it greater then the dead zone it is 'on'. The units dead zone/activation point values correspond to 1.0 for a totally activated trigger/stick and 0.0 for one at their lowest value/centre point. For example if the dead zone for a controller stick is to be at 40% of the maximum value then you would set the dead zone value for that stick to 0.4.
#### Sensitivity
New values are multiplied by the sensitivity value. Sensitivity does not affect digital channels.
#### Auto-zero
After the new value is set it is set back to whatever the default value for the value type is, ex. 0.0 for floats, false for booleans etc.
#### Always notify listener
Listeners are notified whenever a new value is set, regardless of whether the value changes or not.
#### Bound
All values greater than a threshold are set to a certain value.
