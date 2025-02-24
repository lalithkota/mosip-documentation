# Packet Manager

## Overview
Packet Manager performs the following functions:

1. Reads/writes registration packets from/to [Object Store](storage.md#object-store).
1. Performs in-memory encryption and decryption of packets. 
1. Performs security checks, checksum, file validations, ID object validations etc. on the registration packet.
1. Provides packet information to other services via APIs. In case of multiple packets associated with an ID, pulls information from packets based on configured priority. (See [`packetmanager.default.priority`](https://github.com/mosip/mosip-config/blob/develop3-v3/application-default.properties)).

Packet Manager runs as a service and is also available as a library. 

![](_images/packet-manager.png)

The relationship of Packet Manager with other services is explained here. _NOTE: The numbers do not signify sequence of operations or control flow. Arrows indicate data flow_.

1. [Resident Services](resident-services.md) uses Packet Manager library to create packet.
2. [Registration Processor](registration-processor.md) reads packet data using Packet Manager service.
3. Packets are stored and retrieved from [Object Store](storage.md#object-store).
4. Audit logs.
5. Encryption and decryption of packet. 
6. [Registration Client](registration-client.md) uses Packet Manager library to create packets.

## Packet stucture
Refer [Registration Packet Structure](registration-packet-structure.md).

## API
Refer [API Documentation](https://mosip.github.io/documentation/release-1.2.0/release-1.2.0.html).

## Source code 
[Github repo](https://github.com/mosip/packet-manager/tree/release-1.2.0).



