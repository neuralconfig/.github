# neural\[config\]

I'm a network engineer with 20+ years of enterprise infrastructure experience (CISSP, CCNP, CWDP/CWSP) who builds AI-powered tools that solve real network operations problems. Most of my projects started the same way — I was doing something manually, realized it followed a pattern, and built a tool to handle it.

## Featured Projects

### [device-profiler](https://github.com/neuralconfig/device-profiler)

**Problem:** IoT and headless devices can't do 802.1X authentication, so they
land on a quarantine VLAN and stay there until someone manually profiles and
provisions them.

**Solution:** A seven-stage profiling pipeline that combines Fingerbank API
lookups, MAC vendor matching, Nmap port scanning, DNS pattern analysis, PoE
power draw, LLDP data, and DHCP hostname fingerprinting into a weighted scoring
system. Each method contributes a confidence score, and the aggregate determines
device classification. A state machine moves each device through discovery →
fingerprinting → classification → RADIUS registration → production VLAN,
targeting ~30 seconds end-to-end.

**Stack:** Python/FastAPI backend, React dashboard, Cloudpath RADIUS integration.

### [osticket-agent](https://github.com/neuralconfig/osticket-agent)

**Problem:** Network support tickets ("move port 3 in room 214 to VLAN 100")
follow predictable patterns, but still require a human to SSH into a switch,
run commands, verify the change, and update the ticket.

**Solution:** An autonomous agent using Claude 3.5 Haiku and HuggingFace's
smolagents framework. The agent polls osTicket for new tickets, interprets
what's being asked, SSHs into the correct RUCKUS ICX switch, executes the
changes (VLAN assignments, port enable/disable, PoE control), verifies the
result, and closes the ticket.

**What makes it interesting:** Not a chatbot. The smolagents agentic loop means
the LLM reasons about which tool to call, interprets switch output it hasn't
seen before, and decides whether to retry or escalate. Four-layer architecture:
network operations → AI tool wrappers → osTicket API client → agent framework.

### [ruckus-ztp](https://github.com/neuralconfig/ruckus-ztp)

**Problem:** Provisioning new RUCKUS ICX switches requires manual console
access, firmware updates, and configuration — time-consuming and error-prone
at scale.

**Solution:** A distributed zero-touch provisioning system. Edge agents
(Python services deployed on-site) discover switches via LLDP, handle the
full provisioning workflow locally, and stream events to a cloud dashboard.
Four interfaces to the same engine: edge agents, a React web dashboard, a
native SwiftUI iOS app for field technicians, and an AI chat interface
(OpenRouter) for natural language provisioning commands.

**Notable:** Edge agents keep working when cloud connectivity drops — ZTP
doesn't stall because a dashboard is unreachable. MAC-based device tracking
prevents duplicate provisioning when DHCP leases change.

### [r1-api](https://github.com/neuralconfig/r1-api)

**Problem:** RUCKUS One is a cloud network management platform with a REST API
but no official Python SDK, making automation painful.

**Solution:** A Python SDK covering ~85% of the core API, organized into
modular namespaces (venues, APs, switches, WLANs, clients, DPSKs). Handles
OAuth2 token lifecycle, provides typed responses, and ships with CLI utilities
for common operations: bulk AP reboots, support log collection, L3 ACL import
from CSV, and inventory reporting.

**Demonstrates:** Library design — clean public API, separation of HTTP
transport from domain logic, consistent patterns across namespaces.

## Technology Stack

*Only technologies used in the repositories above.*

**Languages:** Python, JavaScript/Node.js, Swift

**AI/LLM:** Claude API (Anthropic), OpenRouter, HuggingFace smolagents, LlamaIndex, ChromaDB, Ollama

**Data:** Pandas, NumPy, SQLite

**Web:** FastAPI, Flask, React

**Infrastructure:** Docker, Google Cloud Functions

**Network:** RUCKUS (SmartZone, R1, ICX), NetMiko, SSH, SNMP, LLDP, RADIUS

## Background

**Certifications:** CISSP, CCNP, CWDP, CWSP, Ekahau ECSE

**Education:** Stanford Machine Learning Specialization, HuggingFace AI Agents Course

**Experience:** 20+ years enterprise network infrastructure — design, deployment, and automation

## Contact

Email: [contact@neuralconfig.com](mailto:contact@neuralconfig.com)
Website: [neuralconfig.com](https://www.neuralconfig.com)
LinkedIn: [NeuralConfig](https://www.linkedin.com/company/neuralconfig)
