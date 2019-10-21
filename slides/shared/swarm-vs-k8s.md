# Swarm or Kubernetes?

- People want a clear answer, but there isn't one.. but in general:

--

- Swarm is an optional feature inside Docker Engine:

--

  - Swarm is easiest to get started, and manage. Runs everywhere Docker does (Linux, Windows, ARM, 32-bit, mainframe, IoT, embedded, and more)

  - But Swarm is mostly maintained by Docker Inc and has limited 3rd party support and plugins

--

  - More popular for "solo DevOps" up to teams with "normal" requirements (e.g. not Netflix or Google)

  - But also used by Visa and PayPal for all Black Friday transactions, and the majority of Docker Inc's [800 enterprise customers](https://www.docker.com/customers) like ADP, Virginia Tech, and MetLife

--

  - Feature UI/UX is very streamlined, ideal for developers and operators, and follows 80/20 rule

---

## Swarm or Kubernetes cont

- Kubernetes is a series of containers on top of Docker Engine (or other container runtimes):

--

  - Designed for enterprise operators as API to build higher-level abstractions on, not ideal if upstream used directly
  
  - Hence so many "distributions" that add value on top of K8s core

--

  - Requires more resources, management, people, and skills to run yourself
  
  - But every cloud offers a distribution to take *some* pain away

  - Also supports more use cases, features, methodologies, and workflows then Swarm

--
  
  - Is the de facto standard orchestrator, and has "won the Internet" hearts and minds
  
  - Nearly all container vendors are "Kubernetes first"

---

## Swarm or Kubernetes cont

- Both orchestrators:

  - Run containers on one or more Linux or Windows machines
  
  - Scale to thousands of nodes and 10's of thousands of containers
  
  - Can provide high availability, security, and encryption at every level

--

  - Provide open source and paid support versions
  
  - Are well documented and have been in production for 3+ years
  
--

  - Solve tons of problems around deploying apps in containers to a set of servers

  - Run on any cloud or in any datacenter

---

## OK great, but seriously which one?

- "We're required to run Kubernetes" is common. Your choice is made

--

  - Tech tool decisions are not purely about features

--

  - Other factors: Existing vendor relations, ideology, team expertise, bragging rights

--

- For learning? Learn Docker, then Swarm (built-in), then Kubernetes

--

- Teams have left Swarm for Kubernetes, vice versa, or even run both side-by-side


- There is no one-size fits-all solution

---

## Bret's Inside Scoop: VHS vs. Betamax

- Don't always believe the Internet: 

--
  
  - Swarm is not dead and Kubernetes is not the only option

--
  
  - Kubernetes can be complex but distributions make it easier

- Some pride themselves on using upstream "Vanilla Kubernetes"... why??

--

- Kubernetes: bleeding edge of infrastructure automation and experimentation

- New features refine expirence, getting more stable

- Kubernetes now supports Windows Server 2019


--

- Swarm is slowly getting more features, but is dwarfed by k8s options

- Docker's tight partnership with Microsoft: Windows Server 2016+ support
  

---

## Bret's Inside Scoop: listen to the creators

- Pay attention to orchestration founders:
  
--

  - The creators of Kubernetes designed it for enterprise ops

--

  - Not to be used directly, but rather by higher level abstractions (distributions)

--

  - Life Tip: Tools are sometimes used in ways other than the creators intended
 
--
  
  - Swarm maintainers goal: take popular orchestration features and make them easy for all

--

  - Docker founder predicts eventually all orchestrators will be 90% same

--

  - Rancher founder made K3s as a joke because K8s was too big/hard. Now it's a thing

--

  - Rancher founder said K3s is "trying to make K8s as easy as Swarm"

---

## Bret's Inside Scoop: usage and echo chambers


--

  - In all industry surveys from 2018 (4+), both are increasing adoption and market share
  
--

  - DockerCon: People love Swarm *and* Kubernetes for different reasons
  
--

  - Swarm is mostly developed by Docker, and run by 80-90% of their paying customers
  
--

  - No one is paid to promote Swarm
  
--

  - Kubernetes is mostly developed by Google and RedHat

--

  - Thousands of people are paid to promote Kubernetes across the whole industry
  
--

  - KubeCon: 10k ppl, more ops focused. DockerCon: 5k ppl, more dev focused
