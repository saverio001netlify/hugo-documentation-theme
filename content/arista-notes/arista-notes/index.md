---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Arista Notes"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2022-03-02T00:02:14+01:00
lastmod: 2022-03-02T00:02:14+01:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

- [Arista EOS - Smart System Upgrade](https://www.arista.com/assets/data/pdf/Whitepapers/SSU_Paper_2014.pdf) \
  A bit like Graceful restart, upgrade sw components while keeping forwarding state and answering keepalives.


- [BGP `GRACEFUL_SHUTDOWN` (formerly `GSHUT`)](https://datatracker.ietf.org/doc/html/rfc8326) \
  As part of the Graceful Shutdown process, `GRACEFUL_SHUTDOWN` is a community to be sent before
  a link or node shutdown. \
  The receiving router should set the `LOCAL_PREF`
  attribute to a low value. 
  
- [DCB and PFC](https://www.juniper.net/documentation/us/en/software/junos/traffic-mgmt-qfx/topics/concept/fibre-channel-cee-features-understanding.html) \
  Data center bridging (**DCB**) is a set of enhancements
  to the IEEE 802.1 bridge specifications. DCB
  modifies and extends Ethernet behavior to support 
  I/O convergence in the data center.
  PFC

  **PFC** is a link-level flow control mechanism similar
  to Ethernet PAUSE (described in IEEE 802.3x). 
  Ethernet PAUSE stops all traffic on a link for a 
  period of time. PFC enables you to divide traffic
  on a link into eight priorities and stop the traffic
  of a selected priority.

  https://docs.google.com/presentation/d/1mfFE6xM-boqlY40i_uqHkK-sZcc3UAvqUcnx-6BVNgY/edit#slide=id.gd66cb94a49_0_459

- [BGP dynamic peers and peer filters](https://www.arista.com/en/um-eos/eos-border-gateway-protocol-bgp) \
  Arista allows to specify a prefix and a range of ASs for a BGP peer group; only
  incoming connections from that prefix and AS range will be accepted.

      router bgp 65000
        bgp listen range 10.0.0.0/8 peer-group DC peer-filter my-as-list

      peer-filter-group my-as-list
        20 match range 65500-65500 reject
        30 match range 1-65535 accept

- [VARP](https://www.arista.com/en/um-eos/eos-varp) functions by having each switch
  respond to ARP and GARP requests for the configured router IP address with the
  virtual MAC address.
  The virtual MAC address is only for inbound packets and never used in the source field
  of outbound packets.

- [GARP (Gratuitous ARP)](https://www.arista.com/en/support/toi/tag/garp)
  Unsolicited ARP messages periodically sent by network elements to advertise their
  IP addresses.
  

