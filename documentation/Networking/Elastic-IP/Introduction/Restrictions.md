# Use Restrictions

Please keep the following restrictions in mind when using the Elastic IP.

- Currently, JD Cloud & AI supports a maximum of 10 Elastic IPs are created for each region, including Standard Elastic IP and Edge Elastic IP. If more quotas are required, please create case for application.

- Elastic IP can associate only with the resource in the same region (including Virtual Machine, container, Load Balancer, and NFV instance). The Standard Elastic IP can only associate with resources in central availability zone under the same region while the Edge Elastic IP can only associate with resources in the same edge zone under the same region; Elastic IPs without a specified IP type are Standard Elastic IPs by default.

- Elastic IP in the Virtual Private Cloud supports associating Elastic IP with Virtual Machine, container, Load Balancer, or NFV only at the ratio of 1:1.

- The bandwidth set when creating Elastic IP is outbound bandwidth, namely the bandwidth for access to public network from JD Cloud & AI.

- For single Elastic IP, multiple associations/disassociations can be performed in a day. If it is required to change the IP of the resource that has associated Elastic IP, the resource shall be disassociated from current IP before associating with a new IP.

- The billing methods for Elastic IP include monthly package, pay by configuration, and pay by consumption, which all support the increase or decrease of the upper limit of bandwidth. For the Elastic IP with Monthly Package, the amount difference before and after the adjustment of bandwidth will be converted into the use duration of the Elastic IP after the adjustment.

- The attribute of IP Availability Zone is the Elastic IP of "Availability Zone A" only associating cloud resources such as Virtual Machines, container, POD, NFV Instance under Availability Zone A, while the Load Balancer and Elastic Network Interface cannot be associated for application.

