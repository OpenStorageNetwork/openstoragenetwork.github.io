---
title: Why use OSN?
prev: docs
# TODO: fix after quick start is done
# next: quick-start
next: overview
weight: 1
---

In every field, data presents a challenge to researchers. Whether you
need to **collaborate on a dataset** with colleagues across institutions, 
compute systems, and geographical locations, **share data with the community**
to meet grant expectations, **integrate data transfer or hosting** into a
research pipeline, or **host data for a science gateway**, the Open Storage
Network (OSN) can help.

### Simplify collaboration

Collaborating across institutions is critical to advance research. However,
handling data across disparate infrastructure is challenging. OSN provides 
a platform to store collaborative data that's not tied to one university or
computing platform. Whether you work on laptops, clusters, or cloud platforms, 
you and your colleagues can use OSN as a central location to store and transfer
research data.

### Host public datasets 

OSN makes it easy to add to your research community's data collection or 
adhere to NSF or NIH data distribution requirements. When you create a storage
bucket, you can either flag it as anonymous access for fully public read access to your
data, or distribute read-only access keys to community members. 

### Add storage to a research pipeline

Research computing pipelines can be complex and involve multiple instruments, computers, 
and locations. OSN fits seamlessly into many pipeline managers, including
[NextFlow](https://www.nextflow.io/docs/latest/amazons3.html),
[SnakeMake](https://snakemake.readthedocs.io/en/stable/snakefiles/storage.html),
and [MLFlow](https://mlflow.org/docs/latest/tracking.html), to simplify data storage 
and transfer along the pipeline. If you're not using a pipeline manager, you can integrate
OSN into any script using [widely-available S3 libraries]({{< relref "tips#tools" >}}).

### Host data for a science gateway

OSN is ideal for hosting data to feed [science gateways](https://en.wikipedia.org/wiki/Science_gateway) or web applications for research distribution or community outreach. 
Whether you're deploying a [Shiny app](https://shiny.posit.co/r/articles/build/persistent-data-storage/#s3), hosting a static [ArcGIS App](https://enterprise.arcgis.com/en/server/latest/cloud/amazon/strategies-for-web-application-deployment-on-aws.htm#GUID-6DD0BE13-4341-435F-8B2C-73282186159D), or building a compute gateway using
[Tapis](https://tapis.readthedocs.io/en/latest/technical/files.html#listings-and-s3-support),
OSN can support your data needs.

## OSN features

OSN provides petabytes of S3 object storage to researchers and educators
through [the NSF's ACCESS program]({{< param "links.access" >}}) or through
[institution-hosted pods]({{< relref pod-hosts >}}). Unlike a typical filesystem,
S3 storage is easily sharable and accessible from any computer.
OSN's storage is a web of "pods" interconnected
by national, high-performance networks. OSN features include

- Data access anywhere via a RESTful interface that follows S3 conventions
- Federated identity management, including through 
  [the NSF's ACCESS program]({{< param "links.access" >}}),
  InCommon, or commercial services.
- High speed data access and transfer via national research and education
  networks.
- Data security and integrity.