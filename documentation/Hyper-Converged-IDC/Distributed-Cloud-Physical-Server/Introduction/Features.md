# Features

JD Cloud & AI's Distributed Cloud Physical Server mainly provides the following functions. For more functions, please access [JD Cloud & AI Console](https://console.jdcloud.com/overview):

- **Rich Edge Nodes:**
Cover domestic edge nodes. At present, East China-Taizhou (Telecom 1) has been opened while other nodes are in preparation and will be successively opened later.
- **Multiple Instance Types:**
Provide two instance types, namely edge computing and edge storage. Now, different and specific specifications are launched to meet different business scenarios of the user. For details, please refer to [Product Specifications](../Introduction/Specifications.md). More instance types are in preparation.
- **Flexible Billing Method:**
2 billing methods, i.e., Monthly Package and Pay By Configuration are supported. The user may purchase based on their demands to save costs. For details, please refer to [Billing Rules](../Pricing/Billing-Rules.md).
- **Rich Image Resources:**
Support CentOS (6.6, 7.1, 7.2 and 7.5) and Ubuntu (18.04, 16.04 and 14.04), as well as multiple common application software installation. For details, please refer to [Image Support System](../Operation-Guide/Image/Description-Image.md).
- **Four Disk Types:**
Four hard disk types, i.e. SAS, SATA, NVME and SSD, are reasonably combined and integrated in the Distributed Cloud Physical Server to provide users with high-speed and reliable bucket.
- **Provide four modes, i.e. NO RAID, RAID0, RAID1 and RAID10:**
If there is one system disk, provide RAID0; if there are two system disks, provide RAID1 mode. Based on the capacity and quantity of data disk, we selectively provide four modes, i.e. NO RAID, RAID0, RAID1 and RAID10. For details of corresponding machine models supporting RAID modes, please refer to [Product Specifications](../Introduction/Specifications.md).
- **Two Types of IP Address:**
Support public IP and private IP, intranet interconnection is achievable, and Internet is accessible.
- **High-speed Network Access:**
Intranet interface and public network interface are 10-gigabit network interfaces. The bottom data network of JD Cloud & AI data center is 10-gigabit level, to ensure the communication quality of intranet.
- **Firewall Setting:**
Set customized instance network access control via iptables firewall to configure different identity and access management rules for different instances. For firewall operation steps, please refer to [Firewall Setting Steps](../Operation-Guide/Network-And-Security/Steps-Network-And-Security.md).
- **Isolated Network Architecture:**
The high-speed network devices of JD Cloud & AI data center are relied on to achieve the intranet interconnection, and provide a high-quality, high-speed, and low-delay intranet environment. The intranet of users is isolated from each other, being secure and reliable.</br>
It supports self-planned network deployment, including preset/non-preset network range (CIDR), subnet segment and intranet CIDR segment that users can choose depending on their preference.</br>
The double upper-link network adopts the bond redundancy policy of IEEE 802.3ad dynamic link aggregation mode, and supports network interface redundancy disaster recovery to guarantee the high availability of network.</br>
Elastic IP can be independently applied for. The public network bandwidth can reach a maximum of 10000Mbps (10000Mbps is the maximum bandwidth that can be provided. The bandwidth may vary depending on various nodes, please make a reasonable choice according to actual node) and be dynamically expanded, supporting association and disassociation.

- **Quick Batch Deployment:**
Automatically deploy the operating system when creating the Distributed Cloud Physical Server, and allow users to reinstall the operating system.

