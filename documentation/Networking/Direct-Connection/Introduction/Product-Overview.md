## Product Overview

The Direct Connection Service is a high-speed, secure and stable network access service provided by JD Cloud & AI. It enables the intranet communication, data backup, and cross-machine room disaster tolerance between JD Cloud & AI network and the network environment of your IDC and partners, so as to provide the user with multicloud Solutions.

Direct Connect involves four products: Border Gateway, VPC Attachment, Direct Connect and Hosted Connect. The Direct Connection comprises the Physical Connection and the Private Virtual Interface, and the Hosted Connect comprises the Hosted Connection and the Hosted Private Virtual Interface.

* Border Gateway: The gateway to host the communication between VPCs and between VPC and external device/environment currently have the functions such as Direct Connection, Cabinet Service, VPN Connection and VPC Attachment.
* VPC Attachment: Interconnection APIs between JD Cloud & AI VPC and Border Gateway.
* Direct Connection: Connect the machine room of JD Cloud & AI and your IDC machine room through physical links to realize Intranet-level communication between JD Cloud & AI network and your IDC network.
* Hosted Connect: Connect the machine room of JD Cloud & AI and your physical equipment in the hosted area of JD Cloud & AI through a physical link to realize Intranet-level communication between JD Cloud & AI network and your network in JD Cloud & AI hosted area.

JD Cloud & AI resources to be connected to Direct Connection: All resources in JD Cloud & AI VPC include Virtual Machines, Container, Load Balancer, Cloud Database, JCS, etc., but the NAT Gateway in VPC cannot be used to unify the Internet exit.

#### Integral Structure

##### Direct Connection Service vs VPN

| Product Advantages | Direct Connection Service | VPN |
|:---:|:---:|:---:|
| Good Network Quality | Access to JD Cloud & AI network through a dedicated physical link, enjoy Intranet-level communication, low network latency and low packet loss rate. | Communicating with shared public network resources cannot guarantee low network delay or packet loss rate.   |
| Safe and Reliable | The physical link is exclusive to the users who access it. Without risk of data leakage, it enjoys high security and meets the needs of customers with high security requirements such as games enterprises, financial enterprises, and government enterprises. | Public network-based encrypted communication, which can meet the security requirements of network transmission for general customers. |
| High Transmission Bandwidth | A single physical link supports a maximum of 10 Gbps of bandwidth, which can satisfy customers with data bulk business. It supports multiple dedicated lines for ECMP, and superimposes the bandwidth limit on the basis of ensuring service availability. | Network bandwidth is limited by the bandwidth of public IP|
| Multiple Access Modes are Available | Supports Layer 2 and Layer 3 access of the network. It is specified while choosing the Direct Connection partner. When you select Layer 2 access, you will run a routing protocol with the public cloud; when you select Layer 3 access, you will run a routing protocol with the partner. Layer 2 access is recommended. | Only supports point-to-point public network transmission|
