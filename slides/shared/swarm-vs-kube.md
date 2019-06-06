## Swarm or Kubernetes?

- People want a black or white answer, but there isn't one.. but in general:

- Swarm is an optional feature built into Docker Engine:

  - Swarm is easiest to get started, and manage. Runs everywhere Docker does (Linux, Windows, ARM, 32-bit, mainframe, IoT, embeded, and more)

  - But Swarm is mostly maintained by Docker and has limited 3rd party support and plugins

  - More popuplar for "solo DevOps" and teams with simpilier requirements

  - But also used by Visa and PayPal for all Black Friday transactions, and the majority of their 800 enterprise customers

  - Feature UI/UX is very streamlined, ideal for developers and operators, and follows 80/20 rule

- Kubernetes is more widely supported/adopted:

  - Runs as a series of containers on top of Docker Engine (or other container runtimes)
  
  - Designed for operators as a raw API to build higher-level abstractinos on
  
  - Usable as vanilla upstream, but not ideal. Hence so many "distrobutions" that add value on top of K8s core

  - Requires more resources, management, and skills to run properly

  - But supports way more use cases, features, methodologies, workflows, etc.
  
  - Is the defacto standard orchestrator, and "won the Internet" hearts and minds

- Both:


---

## OK great, but seriously which one?

- "We're required to run Kubernetes" is common. Your choice is made

--

  - Tech tool decisions are not purely about features

--

  - Other factors: Existing vendor contracts, ideology, team expertese, and deadlines

--

- Both provide open source and paid support versions

--

- For learning? Learn Docker, then Swarm (built-in), then Kubernetes

--

- Teams have left Swarm for Kubernetes, vice versa, or even run both side-by-side

--

- Don't always believe the Internet: Swarm is far from dead, K8s is the only option, 
