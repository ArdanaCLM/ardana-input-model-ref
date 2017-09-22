HCG hcg-wr-s2-mr-kvm-vsa:

This model deploys HCG cloud in a multi region with control plane:
Controller services, database, rabbitmq, mml in a separate
virtual clusters across 2 ardana-hypervisor.
VSA and Swift coexists with virtual control plane and uses raw disks from host
nodes.
Networking for this cloud needs 2 separate interfaces (bonded)
for control and data traffic respectively.
This model supports 2 windriver region with separate PXE network for each
region and shared CLM, BLS, CAN networks.