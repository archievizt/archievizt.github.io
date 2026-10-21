---
layout: default
title: Archie Abeleda
---

# Archie Abeleda

<p class="idblock"><span class="k">ID:</span> Armando Abeleda Jr.<br><span class="k">Run as:</span> Archie</p>

**Network and Security Specialist**

*"Paranoid by trade, boring by design."*

<p class="status"><span class="dot" aria-hidden="true"></span>Systems operational</p>

[CV]({{ '/cv.html' | relative_url }}) · [GitHub](https://github.com/archievizt) · [LinkedIn](https://www.linkedin.com/in/ajrabeleda) · [Email](mailto:hello@archieabeleda.dev)

## About

I know where AI earns its keep on a network, and where it's just confident nonsense.
{: .head}

Over a decade keeping high-stakes networks locked down and online. Belt and braces on every layer. Now I point the same paranoia at my own kit.

Lately my off hours go to pointing AI at the network. A home lab where local models read device state, pull the real config, and reason about it out loud. They get to look and think. They do not get a write path, and nothing reaches a device without going through me first. Same instinct I bring to work, with a lot more freedom to break things.

### Certifications

- [CISSP](https://www.credly.com/badges/00c78370-a452-4af7-bec9-78c4dd4a7720), Certified Information Systems Security Professional
- [CCSP](https://www.credly.com/badges/651c7d74-5b6c-49fd-997b-9a498aa21085), Certified Cloud Security Professional
- [Cisco Certified Specialist (Security)](https://www.credly.com/badges/cd480174-94f9-4bbc-83a9-6b7c5ceb7ab5)
- Cisco Certified Specialist (Enterprise)

### How I work

- **Automation that fires itself.** Python and Ansible doing the repetitive graft, so I never babysit a CLI for it again.
- **Self-hosted AI.** Local models on my own hardware, tuned where the cloud can't watch. Nothing leaves the house.
- **Aggressive segmentation.** Every segment walled off from the rest. Default-deny or it didn't happen.
- **Breaking my own lab.** I break my own lab before anyone else can, because that's the whole point. Better a quiet Tuesday than a Friday night.

Off the clock, I'm usually getting choked out on a jiu-jitsu mat, somewhere in the backcountry with a tent, or reading Stoics who would not approve of my screen time.

---

## Projects

Everything here checks its own work.
{: .head}

A self-hosted lab where I build and break network security and AIOps tools end to end. Real Cisco simulation, real local models, and a security architecture stricter than it needs to be. On purpose.

Tooling
{: .flag}

### Network Automation Toolkit

*The boring, error-prone parts of network ops, handed to code that checks itself.*

**What it does.** Four tools sharing one Netmiko layer, each aimed at a different chore: config backup with drift detection, pre and post change validation, STIG-style compliance auditing with gated remediation, and IPAM sync against NetBox.

**Read-only first.** The tools that only read (backup, audit, pre/post snapshots) run freely. The two that can change a device or a record, remediation and NetBox sync, are dry runs by default. They print exactly what they would do and touch nothing until I add an explicit apply flag.

**How it's built.** A src-layout Python package with a Typer CLI, one command group per tool, everything routed through a single Netmiko connection layer. Inventory and rules are declarative YAML, validated on load, and credentials come from the environment, never the repo. Built and validated in an EVE-NG lab, with a setup guide that takes someone from nothing to a working run.

`Read-Only First` `Python` `Netmiko` `Typer CLI` `Git` `Drift Detection` `STIG Audit` `NetBox`
{: .tags}

[Repository](https://github.com/archievizt/netops-automation) · [Write-up]({{ '/netops-automation/' | relative_url }})

Lab
{: .flag}

### EVPN Fabric with External L3Out

*A spine-leaf EVPN fabric that hands each tenant off to the outside world on its own eBGP session. Every hop proven before I trust it.*

**What it is.** A spine-leaf fabric on Nexus 9000v. OSPF is the underlay and nothing more. The overlay is iBGP with both spines as EVPN route reflectors, so every leaf holds two sessions no matter how many leaves I add.

**The L3Out handoff.** Both leaves double as border leaves. Each tenant leaves the fabric on its own dot1q subinterface and its own eBGP session, into an external IOS-XE router that has no idea EVPN or VXLAN exists behind it. External routes come back as EVPN Type-5 and reach every host inside. Two handoffs, two exits. If one border drops, traffic reroutes across the fabric to the other on its own.

**How I proved it.** It ships as an importable EVE-NG topology with every device config baked in, and a fifteen-point runbook that runs from OSPF adjacency to live border failover. Where the virtual kit falls short of real hardware, the notes say so instead of pretending. CoPP only polices in software here, and a 9000v cannot terminate MACsec at all.

`VRF-Lite L3Out` `OSPF` `iBGP RR` `VXLAN / EVPN` `Type-5` `Anycast GW` `Nexus 9000v` `IOS-XE` `EVE-NG`
{: .tags}

[Repository](https://github.com/archievizt/evpn-vxlan-l3out-lab)

More labs, including the hybrid cloud build, are on the [CV]({{ '/cv.html' | relative_url }}).

---

## Tech stack

The tools that earn their keep.
{: .head}

Over a decade of enterprise kit, plus the self-hosted AI stack I run at home. Grouped by what it does.

- **Network & Security:** `Cisco` `Palo Alto` `Check Point` `Zscaler ZIA` `F5 BIG-IP APM`
- **Perimeter & Access:** `SD-WAN` `IDS / IPS` `NAC` `VPN (IPsec)`
- **Automation:** `Python` `Ansible` `Scrapli` `Netmiko` `Git` `REST APIs`
- **Platforms:** `CentOS` `Ubuntu` `Proxmox VE` `Firebase Hosting`
- **AI Stack:** `Ollama` `Qwen3` `Gemma 4` `nomic-embed-text` `Qdrant` `RAG` `Open WebUI` `OpenClaw` `Gradio`
{: .stack}

---

## Contact

Let's talk.
{: .head}

Networks, security architecture, or pointing AI at infrastructure without it going sideways. Always up for comparing notes.

[hello@archieabeleda.dev](mailto:hello@archieabeleda.dev) · [LinkedIn](https://www.linkedin.com/in/ajrabeleda) · [GitHub](https://github.com/archievizt)

---

*Built with Jekyll, hosted on GitHub Pages. [Source](https://github.com/archievizt/archievizt.github.io).*
