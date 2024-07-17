---
title: OSN User Documentation
draft: true
---

<!-- TODO: Merge with existing docs pages -->

OSN uses the Coldfront resource allocation platform developed by the
Center for Computational Research at the University at Buffalo to manage
storage allocations on the storage network. The Coldfront application is
both open source and provides a plugin framework making it adaptable to
OSN and other third-party requirements. Excellent documentation for the
Coldfront project can be found at the project\'s [documentation
site](https://coldfront.readthedocs.io/en/latest/).

OSN has developed a plugin for the Coldfront application that adds the
ability to manage OSN storage resources. OSN hosts an instance of this
extended Coldfront application at <https://coldfront.osn.mghpcc.org>.
OSN end users and administrators use this application to consume and
manage OSN resources.

# ACCESS vs non-ACCESS Users

There are two ways to request access to OSN storage resources: through
ACCESS or directly from OSN.

[ACCESS](https://access-ci.org/) is a program established and funded by
the National Science Foundation to help researchers and educators
utilize the nation's advanced computing systems. Many types of resource
requests are free for researchers when provisioned through ACCESS and is
a popular way to request OSN resources.

Requests can also be made directly to OSN by sending an email to
<help@osn.mghpcc.org>. This method is most commonly used by network
participants (i.e. organizations that have purchased OSN hardware), by
organizations interested in evaluating the OSN, and for requesting more
information.

# Logon

The logon page presents two authentication options: username/password
and external IdP (the latter via a button labeled \"Log in with
Institutional Account\"); all users must select the Institutional
Account method. Clicking this button redirects the user to a page where
they select from a list of identity providers. Which identity provider
the user should select depends on how they have been granted OSN access.

## ACCESS Users

Users who gain access to OSN via ACCESS must always select the IdP named
\"ACCESS CI (XSEDE)\" when logging into the OSN Coldfront site.

## Non-ACCESS Users

Non-ACCESS users are encouraged to use the ACCESS IdP if they have
ACCESS accounts (note, anyone can setup an ACCESS account if they do not
already have one). For users that don\'t have an ACCESS account and
would prefer not to create one, they can use any identity provider in
the list where they have an account e.g., a college/university IdP or a
cloud provider such as Google, Microsoft or GitHub.

::: warning
::: title
Warning
:::

Your identity within the Coldfront application \-- which determines
which projects you participate on and what you are allowed to do \-- is
directly connected to which IdP you use to logon. Always logon to the
Coldfront application using the same IdP. If you logon via different IdP
accounts the application has no way to know that both of those logons
are \"you\".
:::

# Project Creation

To use the OSN network the first step is to create a project. There are
two different ways to do this depending on whether you are an ACCESS
user or a non-ACCESS user.

## ACCESS Users

1.  **Obtain an OSN allocation via the ACCESS portal** - When ACCESS
    resource providers approve your allocation, commands are sent to the
    OSN Coldfront application that create user accounts, a project, and
    an allocation that allow you use OSN.

2.  **Visit the OSN Coldfront aplication** - Once you\'ve been notified
    that your allocation has been approved by ACCESS, visit
    <https://coldfront.osn.mghpcc.org> and logon.

3.  

    **Logon**

    :   -   Click the \"Login\" button
        -   On the resulting page, click the \"Login with institutional
            account\" button. Clicking this button will redirect you to
            ACCESS where you will select an identity provider (IdP)
        -   In the \"Identity Provider\" drop-down choose the \"ACCESS
            CI (XSEDE)\" option
        -   Click the \"LOG ON\" button; you will be redirected to the
            ACCESS IdP for authentication
        -   Follow the ACCESS IdP authentication steps
        -   After successful authentication, your browser will be
            redirected to the OSN Coldfront application and you will be
            logged on there

## Non-ACCESS Users

1.  **Visit the OSN Coldfront aplication** - Visit
    <https://coldfront.osn.mghpcc.org> and logon.

2.  

    **Logon**

    :   -   Click the \"Login\" button
        -   On the resulting page, click the \"Login with institutional
            account\" button. Clicking this button will redirect you to
            ACCESS where you will select an identity provider (IdP)
        -   In the \"Identity Provider\" drop-down choose an IdP.

        > ::: note
        > ::: title
        > Note
        > :::
        >
        > It\'s recommended to use the \"ACCESS CI (XSEDE)\" option if
        > you have an ACCESS portal account (note that anyone can create
        > an ACCESS account). If you do not want to use ACCESS as your
        > IdP, choose an IdP where you have an account.
        > :::

        -   Click the \"LOG ON\" button - you will be redirected to your
            chosen IdP for authentication
        -   Follow the authentication steps required by your chosen IdP
            (username, password, certificates, 2FA, etc.)
        -   After successful authentication, your browser will be
            redirected to the OSN Coldfront application, which will
            automatically create an account linked to your IdP identity

        > ::: note
        > ::: title
        > Note
        > :::
        >
        > Your automatically generated username (usually your email if
        > that information is provided by your IdP) is displayed in the
        > upper right side of the browser. You will need this in the
        > next step.
        > :::

3.  **Request PI Status** - To request PI status, click your username in
    the upper right of the web page, there you will see a pick named
    \"User Profile\". If you already have PI status, the box labeled
    \"PI Status\" will have a green check mark otherwise, the check box
    will have a red \"X\" and a button next to it labeled \"Upgrade
    Account\". Clicking the upgrade button will create a ticket in the
    OSN support system and a system administrator will review your
    request. If there are any questions, the admin will reach out
    otherwise, they will set your PI status.

4.  **Create a Project** - When notified that PI status has been added
    to your user, logon to the OSN Coldfront application and navigate to
    the projects page (navbar menu pick). On the projects page, click
    \"Add Project\", which will display a form to create your project.
    Enter your project details (name, description, etc.) in the form and
    submit. Your project will be created and displayed.

# Bucket Creation

Once a project has been created users make OSN Bucket allocation
requests to provision buckets on the OSN network. This process is the
same for both ACCESS and non-ACCESS users.

1.  **Navigate to your project** - Allocations are associated with
    projects and you make allocation requests from your project page.

2.  **Request an OSN Bucket Allocation**

    > -   On your project page, click the \"Request Allocation\" button;
    >     a form will be displayed to create your request.
    >
    > -   Select the \"OSN Bucket (Storage)\" resource type for your
    >     allocation request
    >
    > -   In the \"Justification\" text box on the form, enter a
    >     justification.
    >
    >     ::: note
    >     ::: title
    >     Note
    >     :::
    >
    >     **Please include a bucket name in the justification.** OSN
    >     cannot process the allocation request without that
    >     information. Bucket names are restricted as follows:
    >
    >     -   Names must be between 3 and 63 characters long
    >     -   Names may only contain, letters, numbers and hyphen
    >         characters
    >     -   Names must start and end with a letter or a number
    >     -   Names must not contain upper-case letters
    >     :::
    >
    > -   Enter a size in TB in the box labeled \"TB\"

3.  **Wait for Notification** - You will receive a notification from OSN
    when your bucket has been created

4.  **Access Allocation and Bucket** - When notified, visit your project
    and the newly created bucket allocation. The allocation will contain
    the information needed to access your bucket.

# User management

To allow other people to access your bucket allocations, you must add
them to your project and give them access to your allocations. ACCESS
users manage this process through the ACCESS portal; non-ACCESS users
manage using the OSN Coldfront application.

> ::: warning
> ::: title
> Warning
> :::
>
> ACCESS Allocations must be managed through the ACCESS portal.
> Specifically, activities supported both by ACCESS and by the OSN
> Coldfront application, such as adding and removing project members,
> requesting extensions and requesting additional network storage quota,
> must be processed through the ACCESS portal and not using the OSN
> Coldfront application.
> :::

## Non-ACCESS: Managing Users

As a PI for a non-ACCESS allocation you must add users to your projects
and allocations if you want them to be able to access OSN resources. To
do this:

> 1.  Navigate to your project page
> 2.  Click the button labeled \"Add Users\". The resulting page
>     displays a search box.
> 3.  Execute a search
> 4.  On the resulting page, select the allocations that you want the
>     user to have access to in the \"Available Allocations\" section of
>     the page. By default, all allocations are selected.
> 5.  Select the user(s) that you want to give access to in the search
>     results table (under the \"Available Allocations\" box)
> 6.  Click the \"Add Selected Users to Project\" button

# More Information About Coldfront Projects, Allocations and Resources

Coldfront coordinates access to *resources* provided by resource
providers through *projects* and *allocations*.

Resources

:   Resources are systems or instruments that are shared among multiple
    users.

Allocations

:   Allocations reserve a quantity of a resource (e.g. TiB of storage,
    cpu hours) for use by a project.

Projects

:   Projects connect resource users, and resources via allocations.

Coldfront users who are also designated as Principal Investigators (PIs)
may create projects, add users to those projects, and then connect those
users to resources by making allocation requests to resource providers.
See the [Coldfront
documentation](https://coldfront.readthedocs.io/en/latest/) for more
details.

The OSN plugin extends Coldfront and adds two OSN-specific resources to
the application.

## OSN Network Resource {#OSN Resources}

The OSN Network resource represents the OSN storage network. An OSN
Network Resource allocation allows a project and its members to store
data on one or more storage nodes in the OSN distributed storage
network. An allocation of this resource type specifies a quota, which
limits the total amount of data a project may store across the network.

::: note
::: title
Note
:::

A project can have no more than one OSN Network resource allocation.
:::

## OSN Bucket Resource

The OSN Bucket Resource is an object storage \"overlay\" on top of the
OSN Network from which projects may request bucket allocations. A bucket
allocation allows users to store objects on an OSN storage node via the
S3 protocol. A bucket allocation has associated attributes including
quota, bucket name, pod location, and access keys that allow projects to
store and retrieve data.

::: note
::: title
Note
:::

A project can have multiple OSN Bucket resource allocations representing
multiple buckets on nodes in the network.
:::

### Bucket Resource Allocation attributes

Projects users access buckets using the information contained in bucket
resource allocation attributes. The following are the relevant
attributes:

Bucket Name

:   Name of the bucket

Endpoint

:   The path to the bucket\'s OSN pod (e.g.,
    <https://mghpcc.osn.mghpcc.org>)

Read/Write Credentials

:   Each bucket has a read/write access key and associated secret
    attribute. The values stored in these attributes can be used to
    access the bucket with read/write permissions.

Read-only Credentials

:   Each bucket has a read-only access key and associated secret
    attribute. The values stored in these attributes can be used to
    access the bucket with read-only permissions.

Legacy Credentials

:   Buckets created external to the coldfront portal have a legacy
    access key and associated secret attribute. Buckets with legacy
    credentials have custom access permissions.

Anonymous

:   Buckets with the anonymous attribute allow anonymous read access.

Bucket Quota

:   Storage limit for the bucket in TiB.

Pod

:   The name of the OSN Network pod where the bucket is allocated.

Pending

:   Bucket allocations will have a pending attribute when the allocation
    exists in the coldfront system but has not yet been created on a
    node in the OSN network. The coldfront OSN plugin removes the
    pending attribute after a bucket has been successfully allocated on
    an OSN node.
