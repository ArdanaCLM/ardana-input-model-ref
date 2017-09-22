HCG base-hcg-s1-mr-kvm-esx-vsa:

This model deploys HCG cloud in a multi region with control plane:
Controller services, database, rabbitmq, mml, network nodes in a separate
virtual clusters across 3 ardana-hypervisor.
VSA and Swift coexists with virtual control plane and uses raw disks from host
nodes.
Networking for this cloud needs 2 separate interfaces (bonded)
for control and data traffic respectively.
This model supports OVS-DPDK, SR-IOV, PCI-PT, huge pages and
cpu allocations.
Multi-region support.