#GPS
***And other Satellite Navigation Systems***

*Mark Neal, Biology Main*

##What is GPS?
* It gives your location
    * Does not perform route planning
    * Does not perform tracking
    * Does not perform communication
* Constellation of satellites
    * 31 total, 24 active
    * 20,000km "medium earth" orbit
    * Each contains an atomic clock, accurate to 14ns!
    * Developed and maintained by US military
        * Originally conceived for use only by US military, with a "downgraded" version for the public use
* Each sends:
    * Atomic clock time
    * Location estimate of the satellite and other satellites

##How does it work?
* L1 signal 1575.42 MHz
    * Civilian use, unencrypted
    * 50 bits per second
* L2 signal 1227.6 MHz
    * Military, encrypted signal
    * Higher data rate, greater accuracy
* Each satellite transmits 50W, similar to a car headlight
* Will pass through plastic, wood, glass, thin metal surfaces, but not buildings, mountains etc.
    * Can bounce around things to get around obstructions

##Message Format
* PRN, a pseudorandom code which identifies the satellite
* Clock data gives satellites time
    * HOW - Handover Word gives number of epochs
* Ephemeris data - accurate data about satellites own location and future location
    * Repeated every 30 seconds
    * TLM - Telemetry Word (Ephemeris age)
* Almanac data - lower accuracy data about all satellites
    * Repeated every 12.5 minutes
    * Allows the receiver to know which satellites should be in view

##Time to First Fix
* Factory start
    * No almanac or ephemeris data - up to 12.5min to fix
    * Required if no recent fix or moved a long distance since last fix
* Cold start
    * Almanac data is current, but ephemeris isn't
    * Around 30 seconds
*  Warm start
    * All data current
    * A few seconds
* Most units keep almanac/ephemeris data in memory
* Turn your GPS on every day if you don't want a cold start!

##Calculating Your Location
* Measure "time of flight"
    * Compare satellite clock to receiver clock
* Need 3 satellites for 2D fix
    * As we need to sync our clock as well as calculate the position
 * 4+ needed for a 3D fix
 * The more the better
 * Some receivers advertise 20+ channels
    * Pointless - there aren't that many satellites

## GPS Accuracy
* Typical L1 receiver is accurate to ~15m
    * Until 2000 the US government intentionally degraded this to 100m
    * They still have the option to do this
    * US+allied often using consumer equipment for ease of use
* L2 (military) down to a few centimetres
* Altitude measurements less accurate
* Speed and heading estimates accurate over around 1km/h
* US Gov. restrictions prevent use over 999 kts OR 60k ft.
* BUT - L1 receivers can detect relative changes in position down to centimetres
    * Can't tell is this is real movement with just GPS alone

## The Real World Hates You
* Multipath errors
    * Signals bounce of things and reflect
* Atmospheric distortion
* Humidity
* Obstacles block signal
* Interference from other electronics/radios

##Interfacing With GPS
* Traditionally via serial port
    * NMEA 0183 protocol
    * 4800 baud
    * Usually streamed at 1Hz, some units up to 10Hz
* String Format:
    * $GPGGA,092204.999,4350.5589,S.14718.5084,E,1,04,24.4,19.6,M,,,,0000,\*1F
    * Time, latitude, hemisphere(N/S), longitude, latitude, hemisphere(E/W), fix quality, number of satellites, dilution of precision, altitude,,,,DGPS station ID, Checksum

##NMEA Alternatives
* NMEA is not well standardised, official documents are not free or cheap
    * Many manufacturers have proprietry strings, often you can select what strings are sent
    * SiRF receivers can be made to give strings on request
* NMEA2000 uses CAN bus, as used in cars
* SiRF binary protocol, less latency
* GPSD on Linux/Unix
* Locations usually in WG284 datum
    * Datum is approximate geoid of the earth
    * Approximate model of the whole planet, suboptimal for a single country
    * OSGB36 used by Ordnance Survey (OS have their own coordinate system)
        * Most countries have their own datum
        * ETRS89 across Europe

##Improving Accuracy
* Differential GPS
    * Correction signals transmitting the difference in position for a known location
* Most receivers don't output the data required for DGPS
    * Some cheap uBlox and Skytraq units do
    * Software defined radio
* Ordnance Survey gives data for free online
    * 24hrs delay
    * Realtime paid, other countries it's free
