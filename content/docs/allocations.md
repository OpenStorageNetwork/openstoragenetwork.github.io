---
title: ACCESS Allocations
prev: overview
next: portal
weight: 30
---

The Open Storage Network provides S3 storage to researchers through the 
[NSF's ACCESS]({{< param links.access >}}) program. The ACCESS 
program helps researchers and educators use advanced computing systems 
within the United States. ACCESS allocates many types of research 
computing resources at no cost to researchers, including OSN storage.
The following sections will guide you through how to request ACCESS
allocations for OSN storage.

{{< callout note "Institution-owned pod allocations" >}}
If your institution owns an OSN pod, contact your institution's
OSN representative for specific policies and procedures. If
you need help getting in contact, please send a ticket to
{{% help-email %}}.
{{< /callout >}}

## Overview of ACCESS for OSN

Researchers can request OSN project allocations between 10 and 50 Terabytes (TB) through the 
[ACCESS allocation proposal process]({{< param "links.access-allocations" >}}).
If your project needs more than 50 TB of OSN storage, please contact us at
{{< help-email >}}
for options, including purchasing an OSN pod for your institution.

ACCESS allocates resources using a "credit" system. The general process
for this is as follows: 

1. The researcher [submits an ACCESS allocation request](https://allocations.access-ci.org/get-your-first-project). This request includes [a number of credits](https://allocations.access-ci.org/exchange_calculator) and how ACCESS resources would help their project.
2. The researcher redeems the credits to one or more ACCESS resource providers (RPs), including OSN. 

Researchers can redeem ACCESS credits for OSN storage at a rate of **1 ACCESS
credit per 1 GB of OSN storage**. To get started, make a request for 
the minimum OSN project allocation, 10 TB (10,000 ACCESS credits). 
If you need more space, once you near your quota you can make supplemental
storage requests up to a maximum of 50 TB. For a step-by-step guide on how to 
[prepare for]({{< relref "#prepare-for-your-access-allocation-request" >}}) and 
[request]({{< relref "#request-an-access-allocation" >}}) an ACCESS allocation, continue to the following sections.

{{< callout note >}}
[ACCESS Campus Champions](https://campuschampions.cyberinfrastructure.org/) may request 1 TB of storage (1,000 ACCESS credits) for testing. Please
include that you are a Campus Champion in your exchange request.
{{< /callout >}}


## Prepare for your ACCESS allocation request

{{< callout tip >}}
If you're not familiar with the ACCESS process or 
haven't created a project before, ACCESS's helpful
[Get Your First Project Guide](https://allocations.access-ci.org/get-your-first-project)
walks you through the whole process.
{{< /callout >}}

ACCESS allocation proposal requirements vary depending on the scale
of resources requested. When you submit an ACCESS allocation request, consider
what your project needs from any
[ACCESS Resource Provider](https://allocations.access-ci.org/resources) 
you intend to use, including OSN. ACCESS provides a 
[summary table](https://allocations.access-ci.org/project-types)
for project types and requirements and detailed 
[proposal requirements](https://allocations.access-ci.org/prepare-requests)
for each project type.

{{< callout warning >}}
We'll only address the small to medium "Explore ACCESS" and "Discover ACCESS" project
types in this guide. The two large project types, "Accelerate ACCESS"
and "Maximize ACCESS," have more strict proposal requirements
and require a panel review. If you have questions about incorporating
OSN into your large ACCESS allocation projects, please submit a ticket to
{{% help-email %}}.
{{< /callout >}}

### Small projects or first projects

- Submit an "Explore ACCESS" proposal
type for requests up to 400,000 credits. If you're not
sure how much of each resource you need, “Explore ACCESS” is an ideal way 
to get a small ACCESS allocation for test cases and benchmarking. 
- Requirement: A project abstract and minimal justification for the resources requested.

### Medium projects with established resource requirements 

- Submit a "Discover ACCESS" (up to 1.5 million credits) proposal.
- To estimate how many credits you need, first determine how much of each requested resource your project requires, then use the [credit exchange calculator](https://allocations.access-ci.org/exchange_calculator) to convert to ACCESS credits. 
- Requirement: A one-page proposal outlining your project's goals and your need for the specific resources requested.

After you decide on proposal type and ACCESS credit requirements, 
prepare your proposal materials according to the
[ACCESS proposal guide](https://allocations.access-ci.org/prepare-requests).

## Request an ACCESS allocation

To request an ACCESS allocation, use the following instructions.

1. Log in to the [ACCESS portal]({{< param links.access >}}).
2. Navigate to `Allocations > My Projects > Request New Project > Request a <project type> project`.
3. Complete the form with the information and documents you gathered in the [“Prepare for your allocation request”]({{< relref "#prepare-for-your-access-allocation-request" >}}) section.

### Exchange your ACCESS credits for OSN storage{#exchange}

Once your project has been awarded ACCESS credits, you can transfer
those credits for OSN storage and other resources. To exchange your credits, use the following instructions.

1. Go to the [ACCESS allocations page]({{< param "links.access-allocations" >}}).
2. Click the project you want to exchange credits for to expand the information window.
3. In the **Credits & Resources** tab, find the **Add resource to your exchange** field and select **OSN**.
4. Enter the amount of OSN storage you need in TB (minimum 10 TB).
5. Enter the reason for the exchange. Include detailed information for each resource you’re requesting, including OSN. For small projects, it’s acceptable to explain that you want to evaluate OSN for your project.

{{< callout caution >}}
Your first OSN project allocation exchange should be 10 TB
of storage. After you demonstrate need and 
usage, you can request supplements up to 50 TB.
{{< /callout >}}

After you submit your project, the OSN team and teams from any other requested
resources will evaluate your request and approve your project. After 
you get an email notification that your project has been approved, you're
ready to log into the [OSN portal]({{< relref portal >}}) and request your buckets.
