# Reading Material

[Open Flow Switch Specification v1.3.1](./Reading_Material/openflow-spec-v1.3.1.pdf)

[OS10 Setup Instructions](./Reading_Material/force10-s3048-on_connectivity-guide4_en-us.pdf)

# Setup

## Download Controller

I'm doing this on RHEL8

wget http://repo1.maven.org/maven2/org/onosproject/onos-releases/2.1.0/onos-2.1.0.tar.gz

## Setup OpenFlow on the Switch

### Enable OpenFlow

On the switch run:

    OS10# configure terminal
    OS10(config)# openflow
    OS10(config-openflow)# mode openflow-only
    Configurations not relevant to openflow mode will be removed from the startup-configuration and system will be rebooted. Do you want to proceed? [confirm yes/no]:yes

## Configure

