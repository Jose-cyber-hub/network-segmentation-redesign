# Network Segmentation Redesign

> Bootcamp lab: simulated scenario (TripleTen Cybersecurity, 2026)

## Context
This is a small company network that had grown without a plan: two user endpoints, two critical servers (SQL Server and Windows Server), one switch, one router, and no external firewall. Everything could talk to everything, and two of the servers didn't even have passwords. My job was to look at it the way an attacker would, and then fix it the way the person who has to sleep at night would.

## Problem
A flat network where all devices shared one segment, including
servers with weak authentication and end-of-life systems, so one
compromised host could reach everything.

## What I did
- Redesigned the network into 5 VLANs: users, servers, guests, admin, IoT.
- Defined L3 switch ACLs and a default-deny external firewall.
- Added 2FA and a password policy for sensitive access.
- Designed a jump host with session recording for administration.
- Placed a honeypot in a DMZ to detect scanning and intrusion attempts.
- Planned a patch cycle and centralized logging.

## Tools & methods
Network segmentation, VLANs, ACLs, firewall policy design,
access control.

## Results
A documented segmented design that limits lateral movement and
gives visibility into administrative access.

## Recommendations
IDS/IPS, rules for IoT devices, an incident response plan, and
periodic ACL audits.

## Deliverables
- Report: /Proyecto Sprint 1 Jose Iván Arango Franco.pdf
- Network diagram: /Proyecto Sprint 1 Jose Iván Arango Franco - Diagrama.pdf

## Instructor review
Approved. Highlighted the jump host with session recording and
the documented 5-VLAN design.

## What I learned
Security isn't one big wall, it's layers that don't depend on each other. I also learned that a jump host with session recording gives you something a switch never will: a record of who did what. One thing I want to be upfront about: I left the IoT port rules pending because I didn't have the final device inventory, and I said so instead of making rules up. If I did this again, I'd add a ports-per-VLAN table and specify the 2FA type for users, which my reviewer suggested.
