# GSM/UMTS for embedded systems
*Mark Neal, Biology Main*

## Interfacing Embedded System to GSM and UMTS
* Various ways to interface embedded systems to mobile data networks:
    * EasyGPRS module
    * USB Dongle
    * Ethernet Routers
    * USB/Serial connection to phone

## AT Command
* Standard way of communicating from computer to modem was using AT commands
 ---

# Some Ideas For The Scenario

## Static winches on sea bottom
* Buoy at surface
* Winch unit on sea floor
* Intermediate sensors
* Wind back up when not in use
* String will not be straight - lots of potential for drift
    * Inertia measurement
    * Measure angle of string

| Pros | Cons |
| -----| ---- |
| Cheap | Imprecise |
| | Won't be enough  - will need other forms of measurement |
| | Power? - How much, and how to store? |
| | Recovery? - Communication or retrieval of data |

## Free-floating net
* Similar to static winches
    * Weights on sea floor
    * Surface buoy
    * Intermedia sensors

Similar issues to static winches, with the added issue that it's difficult to retrieve/protect. Winches can wind in, if a glacier falls on the net it will be destroyed

## Autonomous Boat

* Will be destroyed in 4.8 seconds
* Avoid drift
* Power/endurance

## Drone and free-floating sensors

* Fly a drone over the glacier, drop the sensors
* This is a fucking terrible idea
