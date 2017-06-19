---
title: "Evolution of Google Cloud's compute technologies"
layout: post
theme: default
category: building
---
Compute has always been the hallmark of cloud computing. Most cloud providers,
        especially those that really matter (e.g., Microsoft or Google), have
        already laid their own mark by introducing their proprietary compute
        platforms. For example, Microsoft has introduced [Service
        Fabric](https://azure.microsoft.com/en-us/services/service-fabric/), a
        microservices platform supporting stateful and stateless applications
        alike. Google has certainly not stayed idle in this arena and over the
        years has introduced its own steak of platforms, namely [App
        Engine](https://cloud.google.com/appengine/) (a cloud PaaS
        infrastrucutre), [Compute Engine](https://cloud.google.com/compute/) (a
        cloud IaaS infrastructure), and more recently [Container
        Engine](https://cloud.google.com/container-engine/) (a cloud container
        management infrastructure).
        
It is interesting to look at the progression of these platforms, and speculate
on the evolution of Google's cloud strategy over the years.

# App Engine
Google Cloud Platform started its journey with the [App
Engine](https://cloud.google.com/appengine) in 2008. It is a formidable
offering, I might add, but only for those who are willing to abide by its
principles. To be more specific, App Engine introduces a powerful (yet
        restrictive) framework for writing scalable applications, one that is
somewhat too idealistic for the reality of cloud customers. In particular, App
Engine proved not to be a good fit for legacy applications as they effectively
need to be re-written from scratch in order to fit.

This shortcoming, I believe, proved to be App Engine's achilles heel causing
its target application mark to shrink significantly to only new applications
(which are not substantial in its early days). This ultimately rubbed Google
from a well-deserved leader role as a cloud provider.

# Compute Engine
With AWS and Azure scooping up customers by offering a basic ability to run
legacy applications inside Virtual Machines hosted in the cloud, Google must
have felt falling behind. This inconvenient truth, I believe, led to
investments in [Compute Engine](https://cloud.google.com/compute/), an
equivalent offering to competitors in the IaaS space that did away with the
earlier sophistication of App Engine.

With Compute Engine, Google could finally talk customers' language without
appearing to be farfetched (i.e., light years ahead).

# Container Engine
Introduction of [Container Engine](https://cloud.google.com/container-engine/)
marks the third wave of Google cloud's compute technologies. With an initial
nudge of approval from Goole (and [other cloud
        providers](http://www.zdnet.com/article/docker-container-support-coming-to-microsofts-next-windows-server-release/))
containers have proved to be a blockbuster technology taking the cloud industry
by storm.

In addition to Container Engine, Google has also acquainted us with
awkwardly-named platforms such as [Kubernetes](https://kubernetes.io/) (which
apparently is the Greek word for pilot) that tout years of prior experience to
run production workload at Google.

I have always felt that there are huge opportunities for making computing cloud
agnostic, or cloud workloads interoperable between providers. A container being
by definition a self-contained package of code and configuration that can run
*anywhere* may go a *loooong* way towards this eventuality. In this regard,
    containers and Kubernetes may prove to be pieces of a winning strategy that
    make cloud interoperability a reality.

--shkreza

{% include disclaimer.html %}
{% if jekyll.environment == "production" %}
  {% include google-analytics.html %}
{% endif %}
