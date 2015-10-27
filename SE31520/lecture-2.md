#Interoperability
*Chris Loftus, A6 Llandinam*

"Getting two programs to communicate with each other"

## Overview
* Interoperability
* Sockets, remote method-level communication, message-based protocols, XML-RPC, SOAP/WDSL and interoperability
* Introduction to REST
* REST-RPC hybrid architechtures
* REST and Resource Oriented Architechture

## Interoperability...
* The ability for software applications to communicate and exchange data
* Applications can be on different platforms and written in different languages
* Within the same organisation:
    * **Application-to-Application** (A2A)
    * Also called Enterprise Application Integration (EAI)
* Between different organisations:
    * **Business-to-Business** (B2B) integration
* **Middleware** is the software that supports interoperability

## Sockets and Interoperability...
| Advantages | Disadvantages |
| ---------- | ------------- |
| Supported by all operating systems | Need to define application-specific protocols |
| Most languages provide an interface to underlying OS mechanisms | Mapping between different language type systems is hard |
| Support reliable communications where this is required | Lack of distribution services: security, transactions, naming services etc. |
| Support lighter-weight communications where required |  |
| Easy to plug in secure sockets to allow encrypted communications |  |

## Remote Method-Level Communication and Interoperability
* RMI, CORBA (Common Object Request Broker Architechture)
* Marshalling
    * Marhsall parameters and request into form required by underlying protocol
* Unmarshalling
    * Unmarshall incoming protocol data to decide which method to call and the parameters to use

| Advantages | Disadvantages |
| ---------- | ----------- |
| Marshalling and unmarshalling is handled by generated code | Remote method-level technology such as RMI are often language-specific |
| Some distribution services are provided | Method-level communication is better suited to intranets rather than internets (too implementation focused) |
| RMI access to CORBA IIOP (multi-language support) | Focused on synchronous communication - what about asynchronous? |
| Builds on the services provided by Sockets |  |

## Message-based protocols
* In asynchronous communication:
    * Producer puts request at the back of the queue
    * When the server decides it is ready, then it will pop the first item in the queue
    * In the meantime, the Producer will still do other operations 
