HCG base-hcg-x1-sr-kvm-esx-vsa:

This model deploys HCG cloud in a single region with control plane:
Controller services, database, rabbitmq, mml, network nodes in a separate
virtual clusters on a ardana-hypervisor.
VSA and Swift coexists with virtual control plane and uses raw disks from host
nodes.
Networking for this cloud needs 2 separate interfaces (bonded)
for control and data traffic respectively.
This model supports OVS-DPDK, SR-IOV, PCI-PT, huge pages and
cpu allocations.