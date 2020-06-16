# Understanding Virtualization

A completely self contained computer that is running within a host OS.

**Virtualization** takes some of the real physical hardware that we have an allocates some of it to a separate internal system.

**Emulation** is when we pretend to have hardware that we don't have.

In order for virtualization to work, we need to have a CPU that supports virtualization.

### Hypervisor

A hypervisor is the actual host that runs the virtual machine.

**Type 1**: install it just like any other OS onto the system. A type 1 has nothing between it and the system hardware. We then create virtual machines that run on top of that hypervisor itself.

**Type 2**: some type of OS is already installed (Windows, Linux, Mac, etc). Then we install the hypervisor just like we would install any other application. Then we run the virtual machines on top of that. The VM itself doesn't see the actual host OS. The hypervisor is between it and the host OS.

# Advanced Virtualization

We can modify virtual hardware easily, such as add a "drive"

Bridge a VM to connect to same network (and DHCP server) as host OS

Use NAT to put a VM in a unique network ID

Use NAT network to put multiple VMs into a single network ID

# Cloud Computing

Cloud computing moves the VMs "out there", but accessible via IP

Cloud computing enables rapid elasticity, on-demand scaling, and resource pooling

IaaS moves network tasks such as firewalls into the Cloud

PaaS moves the machines into the Cloud so we can concentrate on the apps

SaaS moves apps to the Cloud, such as Google Docs

# Cloud Ownership

Private clouds are owned and used only by a single organization

Public clouds are privately owned, but are available for public use

Hybrid clouds have both private and public aspects

Community clouds are owned by mulitple organizations for their own private use

# Cloud Based Applications

Cloud storage enables access to synchronized saved files from any device

Cloud-based applications move management to the Cloud for e-mail and more

Virtual desktops provide a consistent workspace in the Cloud accessible from any device

Virtual application streaming provides access to apps without installing them locally
