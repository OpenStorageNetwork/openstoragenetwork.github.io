---
title: The OSN Portal
prev: allocations
next: request-bucket
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

### View projects

After logging in, you can view your project list by navigating to `Project > Projects`
in the navigation bar menu. The project list shows each project your user has access to, 
whether you're PI of the project or a user. 

{{< callout warning >}}
If you're an ACCESS user and don't see the project you expect after logging in, 
verify that your user is listed as `<NAME>@access-ci.org` on the right side of the 
navigation bar. If not, please log out and 
[log back in using your ACCESS credentials]({{< relref "#log-in" >}}). 
If you need assistance, please email {{< help-email >}}.
{{< /callout >}}

{{< figure src="project-list.png" alt="OSN project list view" >}}

To view project details, click the linked **"Project ID"** number associated with the project.
The **Project detail view** displays all the information associated with a project, including

1. Project name and details
2. Project user list and roles
3. Allocations
4. Attributes (Metadata)

{{< figure src="project-detail.png" alt="OSN project detail view" >}}

### Manage user permissions

Project managers can also add and edit users on the project detail page.

{{< callout caution >}}
If this is an ACCESS project, you must *add* additional users through the 
[ACCESS portal]({{< param "links.access" >}}), not the OSN Coldfront Portal.
{{< /callout >}}

Project PIs are automatically granted "manager" status. To designate additional
project managers:

1. Click the blue person icon on the right side of the target user's
row to view their project-specific detail page.
{{< figure src="project-edit-user.png" alt="Edit user project-specific details" >}}
2. Toggle their role to "manager" in the **Role** dropdown. 
{{< figure src="user-role.png" alt="OSN user project-specific detail view" >}}
3. Click the **Update** button to save the role change.

### Assign users to specific buckets

Project managers can allow or disallow access to view bucket credentials to
each user in the project. 

{{< callout warning >}}
Disallowing access to a user via the OSN portal does not prevent them from
using existing keys if they have the keys already. If you need to regenerate
a key to fully remove access, email {{< help-email >}}.
{{< /callout >}}

To add or remove a user's access to a certain bucket:

1. Navigate to the "Allocations" section on the project.
2. Click on the "allocation detail" button in the row corresponding with the bucket to modify.  
{{< figure src="bucket-detail-button.png" alt="Bucket detail icon location." >}}
3. Use the "Add Users" or "Remove Users" options to manage access.
{{< figure src="bucket-add-user.png" alt="Add / remove user button location." >}}

{{< callout note >}}
To add a user to a bucket, they must be a member of the project first.
{{< /callout >}}