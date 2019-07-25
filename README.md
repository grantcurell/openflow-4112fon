# Reading Material

[Open Flow Switch Specification v1.3.1](./Reading_Material/openflow-spec-v1.3.1.pdf)

[OS10 Setup Instructions](./Reading_Material/force10-s3048-on_connectivity-guide4_en-us.pdf)

# Overview

# My Configuration

- Controller is running RHEL 8
- I used a S4112F-ON

## Switch Version Info

    OS10# show version
    Dell EMC Networking OS10-Enterprise
    Copyright (c) 1999-2019 by Dell Inc. All Rights Reserved.
    OS Version: 10.4.2.2
    Build Version: 10.4.2.2.265
    Build Time: 2019-01-14T15:15:14-0800
    System Type: S4112F-ON
    Architecture: x86_64

## RHEL Release Info

    NAME="Red Hat Enterprise Linux"
    VERSION="8.0 (Ootpa)"
    ID="rhel"
    ID_LIKE="fedora"
    VERSION_ID="8.0"
    PLATFORM_ID="platform:el8"
    PRETTY_NAME="Red Hat Enterprise Linux 8.0 (Ootpa)"
    ANSI_COLOR="0;31"
    CPE_NAME="cpe:/o:redhat:enterprise_linux:8.0:GA"
    HOME_URL="https://www.redhat.com/"
    BUG_REPORT_URL="https://bugzilla.redhat.com/"

    REDHAT_BUGZILLA_PRODUCT="Red Hat Enterprise Linux 8"
    REDHAT_BUGZILLA_PRODUCT_VERSION=8.0
    REDHAT_SUPPORT_PRODUCT="Red Hat Enterprise Linux"
    REDHAT_SUPPORT_PRODUCT_VERSION="8.0"
    Red Hat Enterprise Linux release 8.0 (Ootpa)
    Red Hat Enterprise Linux release 8.0 (Ootpa)

# Setup

## Setup Controller

### Install Prereqs

    pip-3.6 install ryu

### Setup Virtualenv

    python3.6 -m virtualenv ./app
    source bin/activate

## Setup OpenFlow on the Switch

### Enable OpenFlow

On the switch run:

    OS10# configure terminal
    OS10(config)# openflow
    OS10(config-openflow)# mode openflow-only
    Configurations not relevant to openflow mode will be removed from the startup-configuration and system will be rebooted. Do you want to proceed? [confirm yes/no]:yes

## Configure OpenFlow

### Configure Out of Band Management Interface

    OS10(conf-if-ma-1/1/1)# interface mgmt 1/1/1
    OS10(conf-if-ma-1/1/1)# ip address 192.168.1.20/24
    OS10(conf-if-ma-1/1/1)# no shutdown
    OS10(conf-if-ma-1/1/1)# exit
