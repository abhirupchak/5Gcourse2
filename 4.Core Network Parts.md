**AMF**

AMF has following purposes,

Authentication-Initiated by AMF, UE needs to authenticate itself with network first.

Manages UE Registration-UE changes from disconnected to IDLE mode.

Mobility Management
                  - After registration(device in IDLE mode), only tracking area of UE is known to AMF. Going from one **TRACKING AREA**(group of cells) to another, AMF records new tracking area with ID.
                  - Once device moves from IDLE to connected mode AMF also records the cell(within tracking area) it is in.

![amffunnctions](https://github.com/user-attachments/assets/e2c57524-aedf-497a-a55c-5ab564570374)

**AUSF(authentication)**

![ausf](https://github.com/user-attachments/assets/126a0736-268d-481b-9e28-48aa9a575f18)

There is an authentication vector present in the UDM which is specific to the UE, the AMF, through AUSF sends this vector to UE and challenges it with a random number password. 
Afterwards, AMF records UE response and sends it to AUSF which verifies it.

**SMF**

Establishes and manages PDU session. Contacts PCF for determining QoS flow condition.
The correct UPF is also to be selected by the PDU
SMF interacts with UPF for establishment of PDU session
SMF also allocates an IP address to the UE

![smf](https://github.com/user-attachments/assets/a9a29f27-c2b5-4a0f-b016-0b3a0281ad78)

**UPF**

The UPF is the point of contact between the data network and the control network.
Whenever data packets arrive at UPF, it decides where it needs to route those data packets.
**UPF is the anchor point for the UE, for example a UE has PDU session with a UPF, even if the UE moves from range of one cell to another cell it will still have the PDU to the same UPF**
UPF enforces of QoS(PCF decides which QoS, SMF intimates UPF of this QoS)

![upf](https://github.com/user-attachments/assets/5c2e9292-3543-4494-8f2b-171cd9bb9da1)


**UDM**

Centralized database for all subscribers(contains subscriber information) for a given 5G network.
Tracks which AMF the UE is currently in.
Users can also be restricted from "roaming" in certain tracking areas.

![udm](https://github.com/user-attachments/assets/93675409-ea9e-420e-bd4b-879a9d525d3b)

**PCF**

Makes dynamic decision based on network conditions of UE.
For example, UE is in an area with bad connectivity and wants to make a call, PCF can contact SMF to throttle(accelerate) the data or it can refuse the call.
Also manages service areas(List of allowed and not allowed tracking areas), so if device is in non allowed tracking area PCF can contact AMF to stop this.
PCF also decides what the user should be charged according to PDU QoS

![pcf](https://github.com/user-attachments/assets/7a7c21ad-880c-42b7-8e90-9d82e5409121)

**AF**

External server which communicates with PCF in core netwrok to request packet flow.
eg. AF can request IMF node(voice call service).

