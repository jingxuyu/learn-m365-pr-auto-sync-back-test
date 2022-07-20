Teams supports the ability for users to make voice over IP (VoIP) calls from one Teams client to another. 

Microsoft Teams Calling enables users to make and receive calls from any location, using their work number. Users can connect from Teams to landline and mobile devices through the Public Switched Telephone Network (PSTN).

To enable the Dial Pad tab in Teams and allow its users to make and receive PSTN calls, an organization must provision users for Teams Phone and connect it to the Public Switched Telephone Network (PSTN).

To connect to the PSTN, an organization can choose one of the following options:

* Teams Phone with **Calling Plans**
* Teams Phone with your own PSTN carrier with **Operator Connect**
* Teams Phone with your own PSTN carrier with **Direct Routing**
* A **combination solution** that uses Teams Phone with Calling Plan, Teams Phone with Operator Connect, and/or Teams Phone with Direct Routing

‎:::image type="content" source="../media/teams-public-switched-telephone-network-solution.png" alt-text="Diagram showing Teams voice solutions.":::

### Teams Phone with Teams Calling Plans

Teams Phone with Teams Calling Plans is the Microsoft all-in-the-cloud voice solution for Teams users. This design is the simplest option that connects Microsoft Teams Phone to the Public Switched Telephone Network (PSTN). This configuration enables calls to landlines and mobile phones around the world.

An organization should consider using Teams Calling Plans if:

* Teams Calling Plans is available in its country/region.
* It doesn't need to keep its current PSTN carrier.
* It wants to use Microsoft-managed access to the PSTN.

Teams Calling Plans provides the following functionality:

* You get Microsoft Teams Phone with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the type of service being licensed).

* Deployment or maintenance of an on-premises deployment isn't necessary because Calling Plans operates out of Microsoft 365.

> [!NOTE]
> If necessary, organizations can connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.

‎:::image type="content" source="../media/call-plan.png" alt-text="Diagram showing Teams Phone with Calling Plan.":::

### Teams Phone with Operator Connect

Operator Connect is another option for providing Public Switched Telephone Network (PSTN) connectivity with Teams and Teams Phone.

An organization should consider using Operator Connect if:

* Microsoft Calling Plan isn't available in its country/region.
* Its preferred operator is a participant in the Microsoft Operator Connect program.
* It wants to find a new operator to enable calling in Microsoft Teams.

Operator Connect provides the following functionality:

* **Leverage existing contracts, or find a new operator** - An organization can keep its preferred operator and contracts, or choose a new one from a selection of participating operators to meet its business needs.

* **Operator-managed infrastructure** - An organization's operator manages the PSTN calling services and Session Border Controllers (SBCs), allowing the company to save on hardware purchase and management.

* **Faster, easier deployment** - An organization can quickly connect to its operator and assign phone numbers to users — all from the Teams Admin Center.

* **Enhanced support and reliability** - Operators provide technical support and shared service level agreements to improve support service, while direct peering powered by Azure creates a one-to-one network connection for enhanced reliability.

‎:::image type="content" source="../media/operator-connect.png" alt-text="Diagram showing Teams Phone with Operator Connect.":::



### Teams Phone with Direct Routing

Direct Routing enables Teams Phone to connect through an organization's on-premises Session Border Controller (SBC) to the PSTN using its own telephony carrier.

Direct Routing enables an organization to connect its SBC to a telephony trunk using third-party hardware. It can configure interoperability between its on-premises telephony equipment, including PBX and analog devices, and Teams Phone.

:::image type="content" source="../media/direct-routing.png" alt-text="Diagram showing Direct Routing flow.":::

An organization should consider using Direct Routing if:

* It wants to use Teams with Teams Phone.

* It must keep its current PSTN carrier.

* It wants to mix routing, with some calls going through Calling Plan and some through its carrier.

* It must inter-operate with third-party PBXs or equipment such as overhead pagers, analog devices, and so on.

Teams Phone with Direct Routing provides the following functionality:

* An organization can connect its own supported SBC to Microsoft Teams Phone without the need for other on-premises software.

* An organization can use virtually any telephony carrier with Microsoft Teams Phone.

* An organization can choose to configure and manage this option, or it can be configured and managed by its carrier or partner (assuming its carrier or partner provides this option).

* An organization can configure interoperability between Microsoft Teams Phone and its telephony equipment, such as a third-party PBX and analog devices.

‎Teams Phone with Direct Routing requires the following prerequisites:

* Uninterrupted connection to Microsoft 365.

* Deploying and maintaining a supported SBC.

* A contract with a third-party carrier (unless it's deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Teams Phone with Calling Plan.)

## Basic telephony terminology

If you don't have a foundation in telecommunications, it's recommended that you familiarize yourself with the following terminology:

* **VoIP (Voice over Internet Protocol)** - VoIP or IP phone service enables calls and capabilities such as video calling and conferencing through an internet connection or a dedicated Internet Protocol (IP) network instead of dedicated voice transmission lines (traditional phone service).

  VoIP uses voice over IP technology to convert signals from analog to digital before transmitting them over the internet. VoIP phones and devices work with a voice or video calling app. The calls between Teams clients are VoIP calls.
  
  Calls between users in your organization are handled internally within Teams Phone. They never go to the Public Switched Telephone Network (PSTN). This design applies to calls between users in your organization located in different countries/regions, removing long-distance costs on these internal calls.

* **Public Switched Telephone Network (PSTN)** - PSTN is the complete global telephone network operated by national, regional, and local telephone companies. PSTN provides the infrastructure and services for public telecommunications, including all telephone lines, fiber optic cables, microwave transmission links, mobile networks, communication satellites, and underwater telephone cables, all of which are interconnected with switching centers.

* **Microsoft Teams Phone** - Teams Phone is a Microsoft technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.

  Calls between users in your organization are handled internally within Teams Phone. They never go to the Public Switched Telephone Network (PSTN). This design applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.

* **Private Branch Exchange (PBX)** - A PBX is a [telephone exchange](https://en.wikipedia.org/wiki/Telephone_exchange?azure-portal=true) or switching system that serves a private organization. It enables sharing of central office trunks between internally installed telephones, and it provides intercommunication between those internal telephones within the organization without the use of external lines. The central office lines provide connections to the PSTN, and the PBX permits the shared use of these lines between all stations in the organization.

* **Session Initiation Protocol (SIP) trunks** - A SIP trunk enables an end point’s PBX Teams Phone to send and receive calls through the internet. SIP trunking is a service offered by communications service providers that uses the Session Initiation Protocol to provision streaming media services and Voice over IP (VoIP) connectivity between an on-premises Teams Phone and the PSTN. SIP trunks enable internet telephony service providers to deliver telephone services and unified communications to customers equipped with SIP-based IP PBX and unified communications facilities.

