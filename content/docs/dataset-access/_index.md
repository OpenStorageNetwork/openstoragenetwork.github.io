---
title: Read and Write Data
prev: request-bucket
next: tips
weight: 60
---

Once you have an [allocation]({{< relref allocations >}}) and have [created a bucket]({{< relref "request-bucket" >}}) 
(or, someone [sent you keys or an open access endpoint]({{< relref "request-bucket#sharing-credentials" >}}) ), you're ready to read or write data.


## Dataset types

OSN buckets can be either **open access** or **protected**:

- **Open access buckets** are readable by anyone without credentials ("anonymous access"). 
  Writing new data still requires keys.
- **Protected buckets** require keys to both read and write data.

Protected datasets have two sets of keys. One set allows reading and writing to the
dataset while the second set of keys only provides read access. 
Anonymous access is not allowed on protected datasets. For information on sharing credentials,
see [the bucket documentation page]({{< relref "request-bucket#sharing-credentials" >}}).

## Connecting to OSN buckets

OSN supports a RESTful API that is compatible with the basic data access
model of the [Amazon S3
API](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html). Any
software that complies with that API can access data stored on the OSN.

Here, we describe several popular tools in detail. 
However, there are many more commercial and open source software tools for moving
files to and from S3 buckets. OSN buckets are typically compatible with any 
tool that supports AWS S3.

{{< callout note >}}
Do you have a favorite tool for using OSN that we don't mention here? Let us 
know at {{< help-email >}}!
{{< /callout >}}

## Before you begin

All S3 access methods require

1. The bucket endpoint
2. The bucket name
3. For protected datasets, either the RW Access Key/Secret pair or the RO Access Key/Secret pair

To find this info, see [the bucket attribute descriptions]({{< relref "request-bucket#bucket-attributes" >}}).


## Graphical applications

- [**Cyberduck** (macOS, Windows)]({{< relref cyberduck >}})

## Command line applications

- [**Rclone** (macOS, Windows, Linux)]({{< relref rclone >}})
- [**AWS CLI** (macOS, Windows, Linux)]({{< relref aws-cli >}})

<!-- 
Third Party Data Management
---------------------------

OSN users may also choose to layer more sophisticated data management
applications on top of the S3 API services that OSN provides. Two
applications that have been used with OSN include Globus (using the
Globus S3) connector and iRods. Both packages have detailed descriptions
on how to connect the service with a S3 storage provider.

### Globus with OSN

OSN does not provide a Globus instance. You must provide your own. In
order to use Globus with OSN, you must have the [AWS Web Services S3
Connector](https://docs.globus.org/premium-storage-connectors/v5/aws-s3/)
installed and configured in your Globus instance.

After installing the Globus Connector, you can run the following
commands to configure your OSN bucket as a Globus collection.

Create a storage gateway:

    $ globus-connect-server storage-gateway create s3 collection_name --s3-endpoint https://site.osn.xsede.org --bucket bucket-name --s3-user-credential --domain your.globus.domain

Find the Storage Gateway ID:

    $ globus-connect-server storage-gateway list

Create a Globus collection:

    $ globus-connect-server collection create 12345678-9abc-defg-hijk-lmnopqrstuvw / "collection_name" --organization "Name of your Organization" --contact-email youremail@your.domain

where the string 12345678-9abc-defg-hijk-lmnopqrstuvw is what is
returned by the \"Find the Storage Gateway ID\" command. -->
