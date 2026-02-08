# neural\[config\]

I'm a network engineer with 20+ years of enterprise infrastructure experience (CISSP, CCNP, CWDP/CWSP) who builds AI-powered tools that solve real network operations problems. My projects aren't demos or tutorials — they're tools I built to automate work I was doing by hand.

## Featured Projects

### [device-profiler](https://github.com/neuralconfig/device-profiler)

**Problem:** IoT devices connecting to the network get stuck on quarantine VLANs because traditional profiling methods (MAC OUI, DHCP fingerprinting) aren't reliable enough on their own.

**Solution:** Multi-method device detection that combines MAC OUI lookup, LLDP/CDP neighbor data, DHCP fingerprinting, SNMP queries, and HTTP probing into a weighted scoring system. A state machine tracks each device through discovery, profiling, and classification stages, then pushes the result to RADIUS for automatic VLAN assignment.

**Key decisions:** Weighted scoring over hard rules because no single detection method is reliable for IoT. State machine architecture because device profiling is inherently a multi-step process with retries and timeouts.

### [osticket-agent](https://github.com/neuralconfig/osticket-agent)

**Problem:** Network support tickets ("port 3 in room 214 needs to be on VLAN 100") require a human to read the ticket, SSH into the switch, run commands, verify the change, and update the ticket. Repetitive work that follows predictable patterns.

**Solution:** An autonomous AI agent using Claude 3.5 Haiku and HuggingFace's smolagents framework. The agent reads tickets from osTicket's API, interprets what's being asked, builds an execution plan, SSHs into the correct RUCKUS ICX switch, runs the commands, verifies the result, and updates the ticket — all without human intervention.

**What makes it interesting:** This isn't a chatbot or a script with an LLM bolted on. It's a true agentic loop where the AI reasons about what commands to run, handles unexpected switch output, and decides whether the task succeeded or needs a different approach.

### [ruckus-ztp](https://github.com/neuralconfig/ruckus-ztp)

**Problem:** Provisioning new RUCKUS ICX switches requires manual console access, firmware updates, and configuration — time-consuming and error-prone at scale.

**Solution:** A zero-touch provisioning system with four interfaces: edge agents (Python services running on-site that discover switches via LLDP and handle the provisioning workflow), a cloud web dashboard (React) for monitoring and management, a native iOS app (Swift) for field technicians, and an AI chat interface for natural language provisioning commands.

**Notable:** Four different interfaces to the same provisioning engine, including natural language. The iOS app uses SwiftUI and communicates with the same FastAPI backend as the web dashboard.

### [r1-api](https://github.com/neuralconfig/r1-api)

**Problem:** RUCKUS One (R1) is a cloud network management platform with a REST API but no official Python SDK, making automation require raw HTTP calls and manual token management.

**Solution:** A Python SDK with ~85% API coverage, organized into modular namespaces (venues, APs, switches, WLANs, clients, DPSKs). Handles OAuth2 token lifecycle automatically, provides typed responses, and follows Python library conventions so it feels native.

**Demonstrates:** Library design — clean public API surface, separation of HTTP concerns from domain logic, consistent patterns across namespaces, comprehensive error handling.

## Technology Stack

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
