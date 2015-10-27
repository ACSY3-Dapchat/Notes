Space Robotics: A Survey of Space Robotics paper
====

Comparing:
* What we have now
* Major space challenges
* What we will have in 10 years with nominal effort
* What we will have in 10 years with extreme effort

### Robots for Planetary Surface exploration
Sojourner:
* 1997
* Command sequences run by humans directly
* Had the capability for autonomous navigation which was not used
* Placing instruments on rocks took several days via teleoperation


Terrestrial rovers:
* Multi-kilometre distances covered autonomously
* Examples: K9 and FIDO
* Approach objects autonomously, and place instruments
* Takes less time than human interaction
* Used in Antartica
* Not involved in science data interpretation


Future development:
* Sensor fusion - numerous sources
* Path planning
  * characterisation of obstacles
  * terrain features
* Robot self-awareness:
  * Self-diagnosis
  * Time monitoring
  * Power monitoring
* Humans still involved, but not as much
* Give robot high-level goals, instead of low-level instructions

_ Limitations only caused by physical means - eg. power _

Challenges:
* Replicating human skill:
  * Observation
  * interpretation
  * Prioritisation
  * Adaptability
* "...lack the perceptual and cognitive abilities of a field scientist"

---

### In-Space Operations

Aims:
* Component assembly
* Inspection
* Maintenance
* Component replacement

Where:
* Space shuttles
* ISS

Currently:
* 100% teleoperated
* Simple component assembly
* Ranger & Robonaut (terrestrial) ROTEX (space)
  * More dexterous
  * Under teleoperation
* Skyworker & ASAL (NASA Langley):
  * Autonomous assembly
* AERCam Sprint:
  * Remote inspection tasks

Next 10 years:
* Dexterity will equal or exceed that of a human in a space suit
* Still under teleoperation
* Autonomous work:
  * Careful engineering
  * Inspection seems possible
  * How to over-come safety assurances?

---

## Detailed functionalities

### In-Space assembly

Currently:
* Space Shuttle
* ISS remote manipulator systems (RMS)
* Teleoperated arms
* Move large objects

Testbeds:
* Autonmous movement of large objects
* E.g. Skyworker and NASA Langley's Automated Telescope Assembly
* Teleoperated can do fine work - Robonaut & Ranger

In 10 years:
* Delicate tasks autonomously
* As dexterous as a human in a space suit
* Extra effort:
  * With guidance, build complicated structures
  * With little/no guidance, need tech breakthrough

### In-Space Inspection

_No inspection robots currently_

AERCam Sprint:
* Free-flying camera
* Teleoperated

In 10 years:
* Inspection of exterior surfaces
* Limited autonomous analysis of sensor data
* Extra effort: autonomously inspect exteriors & detect anomalies

### In-Space Maintenance

* Move large objects
* No sophisticated Maintenance
* ROTEX & ETS-VII

In 10 years:
* More dexterous
* Extra effort: Autonomous
* Tech breakthrough needed for autonomous diagnosis and repair of arbitrary faults

### Surface and In-Space Human Assistance:

* [EVA Robotic Assistant](http://ntrs.nasa.gov/search.jsp?R=20030064068)
* Can follow humans
* Carry tools
* Help deploy equipment

ISS & Space Shuttle:
* Move crewmembers around
* Move assembly components

Robonaut & Ranger:
* Hand over tools
* Hold items
* Shine lights

In 10 years:
* Work in proximity of humans (given safety protocols)
* Extra effort:
  * be another team-member
  * Speech
  * Gesture interfaces
  * Physical interaction

### Surface Mobility:

* "...safe and effective navigation in an environment"
* More autonomy, more complexity

Limited autonomy:
* Localise area
* Path-finding
* Obstacle avoidance
* Collect scientific data samples

Increased autonomy:
* Lead to longer durations/distances
* More scientific data collected
* Reduced human Operations
* Monitoring own health
* Plan complex operations itself
* Resource-efficient planning
* Map the area
* Collect data when it thinks it is best

Terrestrial robots:
* Hyperion, Dante & FIDO
* Long distances
* Extreme terrain
* Scientific collection

In 10 years:
* Planning advancements
* Explore extreme terrain
* Complex path-finding and object avoidance
* Mission resource scheduling more sophisticated
* Visual servoing improvements
* Automatic mapping

Extra effort:
* Simultaneous mapping & localisation
* Create maps from several sources such as sensors and orbital data
* Basic autonomous exploration
* Autonomous data collection
* Anomaly detection

Technology breakthroughs needed:
* Power limitations
* Self-reliance - able to travel 1000s of metres
* Traverse cliffs etc
* Derive their instructions from mission objectives

### Surface Instrument Deployment:

Sojourner:
* Several cycles to place instrument on rocks
* APX spectrometer in 1 cycle however

In 10 years:
* Robot, autonomous sample collection
* Track rocks metres away
* Navigate there
* Collect sample from within a few centimetres

K9:
* Deduced reckoning
* Evaluates area
* Where / how to orientate itself and place instrument

Marsokhod, Rocky 7 & FIDO:
* Autonomous approaches
* Use visual systems

Extra effort:
* Extreme terrain
* Occlusions
* Confined spaces


### Science Planning and Perception:

Terrestrial:
* Prioritised list of scientific goals
* Multiple constraints
* Autonomous work in simple environments

In 10 years:
* Robustness
* Autonomy for a day in desert-like places
* Patterns, anomalies and generate plans to collect scientific data

---

## Common Challenges

### Robustness:

* "..continue to function in the presence of faults or anomalous, unexpected conditions."
* Need self-relient robots:
  * Self-diagnosis
  * Recovery
  * Able to survive through temperatures, power, wear and stability
* Need human intelligence - somewhat AI
* Flexiblity
* Direct teleoperation when a robot cannot deal

### Whole-system design:

* Robot unable to work in isolation
* Cannot place a robot in a human situation it was not intended for and assume it will work
* Everything must be considered when designing a robot for a mission:
  * power
  * comms
  * navigation
  * maintenance
  * human interaction
* Studied in great length before any mission

### Mission Competence:

* Humans will never not be involved with space missions
* Even in minor roles such as data analysis
* Challenge is to give more freedom to the robot
* Less continuous operation, more autonomy
* Lets human concentrate on other items at play
* Must let human take over controls when necessary
* Is boring for human to string together each command for robot
* Give robot more powers to decide which action to take next from mission objectives

### Virtual Presence:
* Cognitive presence without being physically there
* Using real-time camera feeds, and labs to analyse rocks, whilst sitting on earth
* Robonaut displays potential
