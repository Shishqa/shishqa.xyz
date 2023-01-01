---
title: kubetos
description: >
  Yet another way to deploy Kubernetes
  (but promising)
---

Aim of this project is to try implementing Kubernetes deployment framework (like Kubespray) with TOSCA standard

> **TOSCA** - (not an opera) - Topology and Orchestration Specification for Cloud Applications, is an OASIS standard language to describe a topology of cloud based web services, their components, relationships, and the processes that manage them.

The project is now at **Proof of concept** stage. I've developed a TOSCA profile for describing a configurable Kubernetes topology, which can be [already used](https://github.com/Shishqa/kubetos) to deploy a Kubernetes cluster.

The main stopper is that xOpera orchestrator (on which I relied at an early stage) does not support substitution mapping and therefore the described cluster description cannot be decomposed into reusable parts.

Now I am working on implementing substitution mapping inside the custom orchestrating system...

To be continued

{{< rawhtml >}}
<details>
<summary>Here you can see a cringe demo video 🌚</summary>
<br>
<div class="is-center">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/s8TprVkiX-c" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
</details>
{{< /rawhtml >}}

