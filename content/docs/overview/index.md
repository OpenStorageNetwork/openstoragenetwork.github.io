---
title: OSN Structure Overview
prev: docs
next: allocations
weight: 20
draft: true
---

The Open Storage Network (OSN) is formed by a web of storage "pods" interconnected
by national, high-performance networks. OSN facilitates collaboration across 
institutions, systems, and geographical locations by providing accessible
storage ideal for transferring and sharing data.

## OSN features

OSN features include

- Data access anywhere via a RESTful interface that follows S3 conventions
- Federated identity management, including through 
  [the NSF's ACCESS program]({{< param "links.access" >}}),
  InCommon, or commercial services.
- High speed data access and transfer via national research and education
  networks.
- Data security and integrity.

{{< figure src="osn-map.png" alt="OSN Pod Deployment as of January, 2021" caption="OSN Pod Deployment as of January, 2021" >}}

## File Systems

OSN Storage is disk based and primarily intended to house active data
sets. OSN storage is allocated from the pod(s) closest to the requestor
with capacity to fulfill the request. Allocations of a minimum 10
terabytes and a maximum of 50 terabytes can be requested through the
XRAS process. If your project needs more than 50 terabytes, please
contact the OSN team directly to discuss before you submit your request.

The OSN supports two types of data sets:

1.  Open Access Data Sets that are readable by anyone and writable by
    Curators and Data Managers.
2.  Protected Access Data Sets that are readable by invitation from a
    data manager and writable by Curators and Data Managers.

Every data set is a collection of objects that are individually and
uniquely accessible from anywhere. For Open Access data sets, an S3
RESTful interface allows users to manipulate storage objects simply by
issuing commands in the form of Uniform Resource Identifiers.

For Protected Access Data Sets, the user first obtains an access key
which is then embedded into the access command. Examples of each are
provided below.

**Coming soon:** Consistent with FAIR principles, every OSN data set
will have a landing page that makes it easy to \"visit\" a data set from
a browser, search engine, or data catalog. The landing page contains
metadata that describes the data set, along with the links to
preconfigured, downloadable tools for accessing the data.

An active research data set can remain in OSN storage for up to five
years and usage must comply with the OSN Acceptable Use Policy.
