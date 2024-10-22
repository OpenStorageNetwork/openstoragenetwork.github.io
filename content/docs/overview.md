---
title: OSN Structure Overview
prev: docs
next: allocations
weight: 20
---

The Open Storage Network (OSN) is formed by a web of storage "pods" interconnected
by national, high-performance networks. OSN facilitates collaboration across 
institutions, systems, and geographical locations by providing accessible
storage ideal for transferring and sharing data.

## OSN features

Key characteristics of OSN storage are:

-   Ability to access data from anywhere via a RESTful interface that
    follows S3 conventions
-   Federated identity management, allowing access to protected
    information with existing identity via InCommon or commercial
    services
-   High speed access and transfer via national research and education
    networks
-   Security and data integrity

OSN storage pods are located in science DMZs at Big Data Hub sites,
interconnected by national, high-performance networks. 5 petabytes of
storage are currently available for allocation.

![OSN Pod Deployment at six sites as of January,
2021](images/osn-map.png){.align-center width="600px"}

![OSN Storage Pod](images/osn-pod.png){.align-center width="600px"}

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
