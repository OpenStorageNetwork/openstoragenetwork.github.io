---
title: The OSN Portal
prev: allocations
next: dataset-types
weight: 40
---

OSN manages resource allocations through the [OSN Coldfront Portal]({{< param "links.osn-portal" >}}). Through the OSN portal, users can view and manage their OSN projects and 
request OSN S3 storage buckets. 

{{< callout warning >}}
ACCESS and Coldfront use the term *allocation* in different ways. Throughout
this guide, **ACCESS allocation** refers to ACCESS credits (described in the [ACCESS allocations page]({{< relref "allocations" >}})), **OSN project allocation** refers to a project's total OSN storage quota in TB, and **OSN bucket allocation** refers to the quota for a specific OSN bucket within a project.
{{< /callout >}}

## OSN portal organization

The OSN portal organizes OSN allocations into two tiers: 

1. **OSN Projects** identify the full allocation and have an *OSN Network Quota (TB)*.
If you're an ACCESS user, this is the amount you requested for your project
during your [exchange request]({{< relref "allocations#exchange" >}}).
2. **OSN buckets** represent one S3 storage bucket within the project. A project 
may have many buckets as long as the sum of the bucket quotas does not exceed 
the project quota.

Within each project, you can view OSN buckets allocated to that project, add
grant and publication information, and view project quota use and descriptive 
information. Additionally, Principal Ivestigators (PIs) can add additional 
authorized users, designate "project managers," and request OSN buckets.

{{< callout note >}}
A user with the "Manager" role in a project can perform the same functions 
as the project PI, including adding other users and requesting OSN buckets.
{{< /callout >}}


## Using the OSN portal

### Log in

1. Navigate to [the OSN portal]({{< param "links.osn-portal" >}}).
2. Click the "Log In" button.
{{< figure src="login1.png" alt="Location of the first login button." >}}
3. Choose the "Log in with institutional account" option. 
{{< figure src="login2.png" alt="Location of the second login button." >}}
4. Choose an identity provider. ***If you're an ACCESS user, you must choose the "ACCESS CI (XSEDE)" identity provider from the dropdown.***
{{< callout caution >}}
In order to use the *ACCESS CI (XSEDE)* identity on OSN, you must have a password
set in your ACCESS account. If your account doesn't have an associated password
or you don't know what it is, visit the [ACCESS Identity portal](https://operations.access-ci.org/identity/new-user-setup#set-reset-your-access-ci-password)
to set or reset your password.
{{< /callout >}}
{{< figure src="access-idp.png" alt="Choosing an identity provider." >}}
5. Log in with your ACCESS username and password or relevant credentials for your identity provider.
{{< figure src="access-pw.png" alt="ACCESS username and password fields." >}}
6. Verify that the username on the navigation bar matches what you expect. If 
you're an ACCESS user, it should say `<username>@access-ci.org (ACCESS)`. 
{{< figure src="logged-in.png" alt="Successful log in." >}}

### Manage project users



### Request OSN buckets

<!-- -   Principal Investigator - Responsible for the allocation and serves
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
    >     OSN Operations -->
