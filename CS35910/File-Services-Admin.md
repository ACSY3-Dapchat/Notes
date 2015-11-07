Internet Admin: File Services Admin
====

*John Gilbey*

### ISO27002
* Confidentiality
* Integrity
* Availability

---------------------

### Back-Up
* Operational Process
* Be able to return the system to a known state

* Is the information:
  * Valid
  * Required
  * Business critical
  * Legally significant
  * Disposable

#### Why Back-up?
* Accidental file deletions / Human error
* Application errors
* Recover to prior (known) state
* Hardware failure
* Disaster recovery / Business continuity
* Legal data-retention requirements

#### What to Back-up?

* Base OS
* Configuration / User environment
* Applications / Layered environment
* Operational data
* User data

#### Where to Back-up?

* Removable media
* Workstation disk
* Server disk
* Network Attached Storage (NAS)
* Storage Area Network (SAN)
* Cloud

|SAN|NAS|
|:---:|:---:|
|Visible to any system on the LAN|Servers & SCSI (Small Computer System Interface) fibre channel|
|Data addressed by file name & meta data (permissions)|Data addressed by block number (raw)|
|Managed by NAS head (typically Linux-based)|Managed by Servers|
||Sits 'behind' servers|
|   |Highly scaleable|

![NAS vs SAN Diagram](http://image.slidesharecdn.com/clusterlythuyetletuanduong06130124-100622081949-phpapp01/95/cluster-ly-thuyet-le-tuan-duong06130124-34-728.jpg?cb=1364508742)

----

#### RAID Levels

##### RAID 0
* Stiped disk array without fault tolerance
* Data in blocks, each block to separate drive
* No parity calculation, simple design
![RAID 0 diagram](http://static.thegeekstuff.com/wp-content/uploads/2010/07/raid-0.png)

##### RAID 1
* Mirroring & duplexing
* 100% inefficient
* 100% redundancy
* Used in financial & other high-availability systems
![RAID 1 diagram](http://static.thegeekstuff.com/wp-content/uploads/2010/07/raid-1.png)

##### RAID 5
* Most used now
* High read transaction rate
* High efficiency
* 3+ needed
![RAID 5 diagram](http://static.thegeekstuff.com/wp-content/uploads/2010/07/raid-5.png)

-----

#### 'Simple' Media Solutions
* Floppy: 360KB - 2.88MB
* Zip: 100-750MB
* Flash: 4MB - 128GB (and bigger)
* CD-R: 700MB
* DVD: 4.7-9.4GB
* DAT: 2-48GB (Digital Audio Tape)
* DLT: 20-80GB (Digital Linear Tape)
* SDLT: 100-300GB

----

#### High - volume solutions
* Enterprise backup systems
* Tape libraries & silos
* Software solutions - e.g. Legato, TiNa
* Backup Agents


#### Environment:

##### Climate:
  * Temperature
  * Humidity
  * Vibration
  * Dust
  * Monitoring / Alarms

##### Access:
* Who?
* Why?
* When?
* Monitoring & Logging
* Competence & Supervision
* Control

##### Constraints:
* SLA / Business requirements
* Staffing
* Manufacturers / Maintainers
* Legal requirements / Health & Safety
* Physical size & density
* Accessibility
* Location

##### Services:
* Power (UPS & Generator)
* Air Con / Climate Control - stop overheating
* Alarms:
  * Heat / Fire / Smoke / Rate of rise (heat)
  * Humidity
  * Water (detect leak from air con)
  * Intruder
* Water
* Normal building services

##### Things to avoid in planning criteria:
* Ground floor
* Basement
* Top floor
* External walls
* Advertising
* Plumbing
* Fire risks

----

*Stephen Kingston*

RAID gives resilience:
  * lose 1 and it's fine
  * lose array = stuffed
  * not backup

> 25 - Redundancy
* "Reliability is often safeguarded by redundancy, or backup services running in parallel ready to take over at a moment's notice"

> 46 - Data Invulnerability
* "Purpose of a backup copy is to provide an image of data which is unlikely to be destroyed by the same act that destroyed the original"
* "Backup copies should be stored at a different physical location to the originals"


#### Backup

##### Tapes:
* Streams data sequentially onto a a tape
* Sequentially is an issue
* Not resilient against silly people
* Not meant to be for recovering lost files

##### Backup Rotation
Good scheme aims to:
  * Reduce backup time
  * Make restores easy
  * Provide wear leveling
  * Account for off-site & long-term backups

##### Back-up data every night?
* No
* Full and incremental backups
* Full backup of x server and backup only changes from the others

##### Schemes:
* Grandfather, Father, Son (Daily, Weekly, Monthly)
  * Levels of backup
  * Daily - take previous day
  * Monthly - take full back up, no incrementals
* Incremented media:
  * Full & incremental backups
  * As above
* Tower of Hanoi
  * Most efficient
  * Complex
  * Hard to restore

------

#### File Transfer

* Sneakernet (Walk your floppy disk to another location)
* UUCP(Unix-to-Unix Copy)
* FTP (using TCP/IP)
* SFTP
* Network Filestore
* HTTP
* [Webdav etc.](https://www.google.co.uk/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0CCMQFjABahUKEwii_Oi-uv7IAhWDdA8KHdtNBDI&url=https%3A%2F%2Fwww.iis.net%2Fconfigreference%2Fsystem.webserver%2Fwebdav&usg=AFQjCNEpUHB_K1OBqJVOB4k7vxJNU0dIVA&sig2=cvrEh_St537VIVJsaRa2tA&bvm=bv.106923889,d.bGQ)

##### FTP:
* Security issues
* Plain text passwords over the network
* Anonymous FTP:
  * Careful configuration needed
  * No method to uniquely identify users

##### Network Filesystems
* Filesystem appears local, except for latency
* NFS
* Root squashing
  * Super user on 1 machine has no privilege on another
* TCP Wrapper (hosts.allow/deny) protects the vulnerable portmapper - covered this in practical!
* Timing issues

> Principle 12: Separation
* Separate OS Data from the file store
* Should be kept in separate directory tree

> Principle 20: Freedom
* Quotas, limits & Restrictions tend to antagonise users
* Users place high value on personal freedom
* Restrictions should be minimised


Datagram networks are unpredictable:
  * Latency

Network clients cache a lot of information:
  *  Local access speeds
  * Until someone else wants to access same file (opportunistic locks)

----

*John Gilbey*

##### Other measures of backup:
* Rate of change
* Immediate value
* Future value
* Recovery time
* Available backup Window
* Review & Removal

##### Necessities:
* Formal statement of service level
* Certified fire safe in separate building
* Daily operations schedule
* Checking, signing and filing of logs
* Operations manual
* Staff training
* 'Live' Disaster Recovery training

##### Complications:
* Proliferation of systems
* Disaster Recovery test opportunities
* Transfer rate
* Backup of open files & databases
* Recovery onto different hardware
* Lack of backup Window
* Technology change
* Media lifetime
