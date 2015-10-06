#Radio Frequency Identification (RFID)

##Basics: System Elements
* **Tags** that contain identifiers
    * It's possible to store additional data and perform other processing, however
    * There are different types of tag
* **Readers** that are used to access the data on the tag
* **Middleware** can take data and link to central IT systems

##Basics: Radio Waves
* Radio waves can carry lots of information
    * Long distance - e.g. TV Signal
    * Medium distance - e.g GSM
    * Short distance - e.g. Bluetooth
* Performing long-range transmission or transmitting more data means using more power
* RFID uses radio waves
    * To talk to very small computers, "tags"
    * For small amounts of data over short distances
    * Tags are used as "smart labels"
* Radio waves can also carry energy
    * They can be used to supply power to the tag.
    * The tags can be:
        * **Passive**
            * Powered completely by radio waves
        * **Active**
            * Powered by battery
            * May also include on-board sensors
        * **Semi-Passive**
            * Communication driven by radio energy

Antenna design and frequency is super important.

* Reader transmits a pulse of RF
* Pulse received by the antenna on the tag
* Some power is diverted to the processor
* An action is performed on the basis of signal. This could be:
    * Transmit information
    * Change state/alter data
    * Kill tag

## Collision Handling

How does a reader handle clashes between tags (multiple tags in the same area)

* **Aloha**
    * Simple approach for small numbers of tags: each tag waits a random time before responding
* **Slotted Aloha**
    * Like Aloha but structured to get one tag to respond in a set timeslot
* **Adaptive Binary Tree**
    * Uses a binary tree to explore the range of tags available, until only one tag responds.

##Reading and Writing Data
* Some tags can be:
    * Read Only (RO)
    * Write Once, Read Many (WORM)
    * Read Write (RW)
* Tags can be invalid or corrupt
    * A study from 2005 suggests that the error rate could be 1/5 for lower-quality tags.
    * However this data is old and the figure is probably much lower now.
