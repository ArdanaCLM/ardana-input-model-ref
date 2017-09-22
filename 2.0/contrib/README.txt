This directroy contains a number of contributed configurations

contrib-1:
  Derived from entry-scale-kvm-vsa
  Deployer on shared cluster
  ARDANA network separate
  Public URLs use IP address
  Tenant VLANs on MANAGEMENT network
  Adds ISCSI network

contrib-2:
  Supplied by Alex Barclay
  Derived from entry-scale-kvm-vsa
  Deployer on shared cluster
  ARDANA network separate
  Combined External API and External VM network
  Public URLs use IP address
  Adds Service network
  NIC mapping includes multi port cards

contrib-3:
  supplied by saratoga
  Derived from entry-scale-kvm-vsa
  Deployer on dedicated cluster
  ARDANA network combined with Management
  Public URLs use IP address

contrib-4:
  Derived from entry-scale-esx
  Deployer on dedicated cluster
  ARDANA network separate, on dedicated NIC
  Seperate External API and External VM network groups
  Public URLs use IP address
  VXLAN on Management Network

contrib-5:
  Derived from entry-scale-ceph
  Deployer on dedicated cluster
  ARDANA network separate, on dedicated NIC
  Separte Ceph cluster and client networks (using hard-coded names)
  Tenant VLANs on Management network
  8, 10, and 12 port NIC mappings
  Separate 3-node MML cluster (Az1, AZ2, AZ3)
  Separate 2-node Swift PACO cluster (AZ1, AZ2)
  Seperate 3-node Ceph Monitor Cluster (Az1, AZ2, AZ3)
  Seperate OSD Cluster (AZ4)
  Seprate Compute (AZ2 & AZ3) and PaaS compute (AZ5)

contrib-6:
  Derived from entry-scale-kvm-vsa
  Deployer on dedicated cluster
  ARDANA network combined with Management
  Public URLs use IP address
  Separate 2-node Core cluster
  Separate 3-node MML cluster
  Separate 3-node MQ/MYSQL cluster
  64 compute nodes

contrib-7:
  Derived from entry-scale-kvm-vsa
  Deployer on dedicated cluster
  ARDANA network combined with Management
  Public URLs use IP address
  104 compute nodes
