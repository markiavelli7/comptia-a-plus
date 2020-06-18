# Installing Windows

First check compatibility

### Know Your Network

If the installation is in an enterpries environment, there will often be a domain and specific naming conventions.

### Know Your Microsoft Account

# Post Installation Tasks

**Device Manager** - Update drivers that aren't recognized be the new Windows installation

**Windows Update** - Make sure that Windows is set up to receive OS updates

**Recovery** - Set up a recovery drive (flash drive has to be at least 16GB)

**Create a Restore Point** - Creates a copy of how the system is right now. If we have a problem in the future, we can roll back the changes. Go into **System Properties/System Protection**, set up restoration, and then set up a restore point

**Anti-Malware/Firewall** - Go into Windows Security settings and check to make sure everything is operational

**File History** - A tool that allows us to keep backup copies of anything that we are changing on a file by file basis.

# Windows Installation Options

**Clean Install** - starting with blank storage and we put installation media in and we install to it from the blank media.

**Upgrade Install** - an upgrade keeps all of our applications, files, and settings. Microsoft will create some limitations to keep things compatible

**Multiboot** - need extra hard drives to install multiple OSes that can be booted from at startup

**Unattended Installation** - we create an answer file, this file answers as many of the install questions as possible during the installation, and will only pop up the screens as necessary. To do this, we use a program called **Windows System Image Manager**. WSIM creates a file called **autounattend.xml** that we add to the .iso installation file.

**Image Deployment** - hardware has to be identical. We take one computer and install Windows on there, applications, networks, etc. We then distribute the image of that system to all of the other computers and simultaneously update all of the individual computers from the one image. Tools like GHOST/Windows Migration Tool let us do Image Deployments.
