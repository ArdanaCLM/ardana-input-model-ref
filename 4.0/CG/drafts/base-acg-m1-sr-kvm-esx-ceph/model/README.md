HCG base-hcg-m1-sr-kvm-esx-ceph:

This model deploys HCG cloud in a single region with control plane:
Controller services, database, rabbitmq, network nodes in a separate virtual
clusters across 3 ardana-hypervisors.
MML are in a separate baremetal nodes.
CEPH are in a separate baremetal nodes.
Deployer and swift run on the host.
Networking for this cloud needs 2 separate interfaces (bonded)
for control and data traffic respectively.
This model supports OVS-DPDK, SR-IOV, PCI-PT, huge pages and cpu allocations.