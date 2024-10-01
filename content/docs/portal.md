---
title: Project Management Portal
prev: allocations
next: dataset-types
weight: 20
---

OSN manages resource allocations through the [OSN Coldfront Portal]({{< param "links.osn-portal" >}}). The OSN portal organizes OSN allocations into two tiers: 

1. **Projects** identify the full allocation and have an *OSN Network Quota (TB)*.
2. **OSN buckets** represent one S3 storage bucket within the project. One project may have many OSN buckets provided the total storage quoted to the buckets is equal to or less than the Project quota. 

{{< callout warning >}}
ACCESS-CI and Coldfront use the term *allocation* in different ways. Throughout
this guide, **ACCESS-CI allocation** refers to ACCESS-CI credits (described in the [ACCESS-CI allocations page]({{< relref "allocations" >}})), **OSN project allocation** refers to a project's total OSN storage quota in TB, and **OSN bucket allocation** refers to the quota for a specific OSN bucket within a project.
{{< /callout >}}


OSN uses the Coldfront resource allocation platform developed by the Center for
Computational Research at the University at Buffalo to manage storage
allocations on the storage network. The Coldfront application is both open
source and provides a plugin framework making it adaptable to OSN and other
third-party requirements. Excellent documentation for the Coldfront project can
be found at the project's `documentation site <CFRTD_>`_.

OSN has developed a plugin for the Coldfront application that adds the ability
to manage OSN storage resources. OSN hosts an instance of this extended
Coldfront application at https://coldfront.osn.mghpcc.org. OSN end users and
administrators use this application to consume and manage OSN resources.

There are four roles associated with an OSN allocation:

-   Principal Investigator - Responsible for the allocation and serves
    as either the Data Manager or the Alternate Data Manager for the
    allocation.

-   Data Manager:

    > -   Adds/removes data curators and data managers
    > -   Adds/removes end users for protected data
    > -   Maintain Data Set Landing Page Information
    > -   Monitors capacity vs utilization and requests allocation
    >     changes when needed

-   The OSN Portal is used by PIs/Data managers to manage their
    allocations. The Portal uses CiLogon for authentication, and
    provides bucket administration tools to the PI/Data Manager who
    requested the allocation. When requesting an allocation, the PI
    provides an identity that is recognized by CILogon. After the bucket
    is created, the PI can log in to the OSN Portal and administer
    access to the bucket.

-   Data Curator - Maintains the data set

-   End User:

    > -   Has read access to all of the data in the bucket.
    >     Public-access buckets allow access to anyone who has the name
    >     of the pod and bucket. Authenticated access buckets allow
    >     access to anyone who has the READ key.
    > -   Registers via any identity service that is trusted by the data
    >     manager (InCommon, ORCID, Github, Google, Amazon, etc.
    > -   Logs in after receiving an invitation from a Data Manager or
    >     OSN Operations
