Internet Admin: Naming and Directory Services
====

DNS:
* Domain Name Service
* Maps hostnames to IP Addresses
* Distributed database
* DNS Servers (client server architecture)

Database vs Directory Services:
* DNS tolerant to getting out of date
* DNS has to respond quickly
* DBs need roll-back, up-to-date information
* DNS is a DISTRIBUTED DB
* No one part to be responding for everyone at the same time

---

#### Before DNS:
* Had to name the computer you wanted to communicated with
* Using hostfile
* Windows:
  * HOSTS
  * LMHOSTS
* Unix:
  * /etc/hosts
* If you want to talk to lots of people, hostfile gets large
* Someone new? They're not in your hostfile
* Files providing name/address mappings
* Still check hostfile before DNS now
* Therefore can 'overwrite' IP addresses for websites you might want to (eg. adware)

#### How is the DNS used?
* Apps access the information in the DNS by way of resolver programs
* nslookup (or 'dig') -> www.google.com -> gives IP address
* google uses load balancing and has 2+ IP addresses
* Common implementation of DNS client and server programs in BIND (Berkeley Internet Domain Server)
* DNS uses a protocol (RFCs) that is used for communication between client & server
* gethostbyname()
* gethostbyaddr()
* RFC = Request For Comments

#### DNS Name Space:

![DNS Name space](images/DNS_Name_Space.png)

* Top level domain names
* 2 letter = country
* UK official code = GB
* In 2000, ICANN approved new, even more now
* NOMINET

* Different people look after the root to the top-levels
* NOMINET = UK
* Each is it's own, owned separately

Domain Name walk - goes root -> points to UK -> points to ac -> etc.

* ARPA does reverse lookups by IP address

#### Where is the root?

![Root locations](images/Root_Locations.png)

* (x,y) x is the # of root servers, y is the # of gTLD servers
* Anycast IP:
  * Same IP addresses, multiple computers
  * Clones of the roots
  * Now all over the world (see below)
  * Still only the 13 original

![Anycast roots](images/AnyCast_Roots.png)

---

#### Name Servers & Zone Boundaries

![Zone Boundaries](images/Boundaries.png)
