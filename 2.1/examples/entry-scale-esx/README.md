## Ardana OpenStack Entry Scale Cloud with ESX Example ##

The input files in this example deploy a cloud with ESX hypervisor that has the following characteristics:


### Control Planes ###

- A single control plane consisting of three servers that co-host all of the required services.

### Resource Pools ###

- Activated vCenter clusters

*EON service will add required information related to compute proxy and OVSvApp Nodes. The user need not add them*

*Minimal Swift Resources are provided by the control plane*

### Deployer Node ###

This configuration runs the lifecycle-manager (formerly referred to as the deployer) on a control plane node.
You need to include this node address in your servers.yml definition. This function does not need a dedicated network.

The minimum server count for this example is therefore 4 servers (Control Plane (x3) + 1 activated vCenter cluster having atleast 1 host)

An example set of servers are defined in ***data/servers.yml***.   You will need to modify this file to reflect your specific environment.


### Networking ###

The example requires the following networks:

IPMI/iLO network, connected to the deployer and the IPMI/iLO ports of all servers

A pair of bonded NICs which are used by the following networks:

- EXTERNAL-API - This is the network that users will use to make requests to the cloud
- EXTERNAL-VM - This is the network that will be used to provide access to VMs (via floating IP addresses)
- MANAGEMENT - This is the network that will be used for all internal traffic between the cloud services and traffic between VMs on private networks within the cloud


TRUNK network is the network that will be used to apply security group rules on tenant traffic.    It is managed internally by Ardana OpenStack cloud and
is restricted to the vCenter environment.

ESX-CONF-NET network (of ESX-CONF network-group) represents a network that is used only to configure the ESX compute nodes in the cloud.  This deployer network should be different from the pxe-based deployer network used by cobbler to standup the cloud controller cluster.

Note that the EXTERNAL-API network must be reachable from the EXTERNAL-VM network if you want VMs to be able to make API calls to the cloud.

The Data Center Management network (which hosts the vcenter server) must be reachable from the Cloud Management network so that the controllers,
compute proxy and OVSvApp nodes can communicate to the vcenter server.

An example set of networks are defined in ***data/networks.yml***.    You will need to modify this file to reflect your environment.

The example uses the devices hed3 & hed4 as a bonded network for all services.  If you need to modify these for your environment they
are defined in ***data/net_interfaces.yml***.    The network devices eth3 & eth4 are renamed to devices hed3 & hed4 using the PCI bus mappings
secified in  ***data/nic_mappings.yml***.    You may need to modify the PCI bus addresses to match your system.

### Local Storage ###

All servers should present a single OS disc, protected by a RAID controller.   This disk needs to be at least 512GB in capacity.
In addition the example configures one additional disk depending on the role of the server:

- Controllers:  /dev/sdb is configured to be used by Swift

Additional discs can be configured for any of these roles by editing the corresponding ***data/disks_\*.yml*** file

