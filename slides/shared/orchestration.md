# What and why of orchestration

* There are many computing orchestrators

* They make decisions about when and where to "do work"

--

* We've done this since the dawn of computing: Mainframe schedulers, Puppet, Terraform, AWS, Mesos, Hadoop, etc.

--

* Since 2014 we've had a resurgance of new orchestration projects because:

--

  1. Popularity of distributed computing

--

  2. Docker containers as a app package and isolated runtime

--

* We needed "many servers to act like one, and run many containers"

--

* An the Container Orchstrator was born

---

## Container orchstrators

* Many open source projects have be created in the last 5 years to:

  * Schedule containers to run on servers

--

  * Dispatch them across many nodes

--

  * Manage container lifecycle operations

--

  * Monitor and react to container and app health

--

  * Provide storage, networking, proxy, security, and logging features

--

  * Do all this in a declarative vs. imperative

--

  * Provide API's to allow extensability and management

---

## Major container orchestration projects

* Kubernetes

* Swarm

* Apache Mesos/Marathon

* Cloud Foundry

* Amazon ECS (not OSS, AWS-only)

* HashiCorp Nomad

--

* **Kuberenetes is the *one* orchestrator with many _distrobutions_**

---

## Kubernetes distrobutions

* Kubernetes "vanilla upstream"

* RedHat OpenShift

* Docker Enterprise (runs both Swarm and/or Kubernetes)

* Rancher

* Canonical Charmed Kubernetes

* And [Many, many more...](https://kubernetes.io/partners/#conformance) (86 as of June 2019)
