---
description: >-
  WORK IN PROGRESS | Infrastructure-as-Code Raspberry Pi 4 multi-node
  micro-Kubernetes Cluster
---

# 😎 Intro

_Documentation and configuration for my attempt to bootstrap and maintain my home-lab_ [_microk8s_](https://microk8s.io) _cluster with_ [_MaaS_](https://maas.io)_,_ [_Ansible_](https://ansible.com)_,_ [_Juju_](https://jaas.ai)_,_ [_Flux_](https://fluxcd.io)_, and_ [_Cloudflared_](https://developers.cloudflare.com/cloudflare-one/tutorials/ssh/)_. The goal is to have a secure-bv-default globally accessible live dev/production environment and server._

## Hardware

[PiKVM](https://pikvm.org) v2:\
\- [Raspberry Pi 4 Model B 4GB](https://github.com/pikvm/pikvm#diy-getting-started)\
&#x20;  \- [AIMOS 8-port HDMI USB-C KVM Switch](https://www.amazon.de/AIMOS-Umschalter-Tastatur-unterst%C3%BCtzen-verbunden/dp/B08FR5K111/)\
MaaS Controllers: \
\- Lenovo Thinkpad T500 | Ubuntu Server 20.04.4 LTS (Linux 5.8)\
\- Acer Swift 3 | Ubuntu Desktop 18.04.6 LTS (Linux 5.4)\
MaaS Server Nodes:\
\- 5x Raspberry Pi 4 8GB\
&#x20;  \- 5x [UASP compatible NVMe M.2 to USB 3.1 Type-C/A SSD Enclosure](https://www.amazon.ca/UGREEN-Enclosure-Aluminum-External-Tool-Free/dp/B07NPFV21K)\
&#x20;  \- 5x [512GB Western Digital Blue NVMe SSD](https://www.amazon.ca/Blue-NAND-500GB-SSD-WDS500G2B0B/dp/B073SBX6TY)\
&#x20;  \- 5x [USB Type-A 3.1 Sandisk 64GB USB Flash Drives](https://www.amazon.ca/SanDisk-64GB-Ultra-Flash-Drive/dp/B077VYCV37/)\
Other relevant (network) hardware:\
\- [8 port Netgear GS108Tv3 Smart Switch](https://www.amazon.com/NETGEAR-8-Port-Gigabit-Ethernet-Managed/dp/B07PS6Z162)\
\- 2x [TP-LINK Archer C7 AC1750](https://www.amazon.ca/TP-Link-AC1750-Wireless-Gigabit-1350Mbps/dp/B00BUSDVBQ) v5 [OpenWRT-21.02](https://openwrt.org/toh/tp-link/archer-c5-c7-wdr7500?s\[]=archer\&s\[]=c7\&s\[]=v5)\
&#x20;  \- 1x Raspberry Pi 3B+ 4GB OpenWRT-21.02

## Steps

1\. This [discourse link](https://discourse.maas.io/t/build-your-own-bare-metal-cloud-using-a-raspberry-pi-cluster-with-maas/5845) is a fully compiled up to date in detail guide on bootstrapping MaaS with a cluster of Raspberry Pis provided directly courtesy of Canonical (Ubuntu) software engineers and all other MaaS contributors.\
2\. Ansible role microk8s\
3\. Ansible role [seaweedfs operator](https://github.com/seaweedfs/seaweedfs-operator#installation)\
&#x20;   \- install [cert manager helm](https://cert-manager.io/docs/installation/helm/) to install seaweedfs operator\
3\. Ansible role cloudflared\
4\. Ansible role gitlab\
5\. Ansible role gitpod\


### Next Steps | TODO

\
Install MaaS and configure \
Use MaaS to provision and deploy RPI cluster\
[https://github.com/papanito/ansible-role-cloudflared](https://github.com/papanito/ansible-role-cloudflared)\
[https://github.com/IanTeda/ansible-microk8s](https://github.com/IanTeda/ansible-microk8s)\
[https://github.com/geerlingguy/ansible-role-gitlab](https://github.com/geerlingguy/ansible-role-gitlab)\
[https://github.com/gitpod-io/gitpod/tree/main/install/installer](https://github.com/gitpod-io/gitpod/tree/main/install/installer)\
[https://developers.cloudflare.com/cloudflare-one/tutorials/many-cfd-one-tunnel/](https://developers.cloudflare.com/cloudflare-one/tutorials/many-cfd-one-tunnel/) -> make into Ansible role\
Add bash aliases and flux autocomplete\
\
