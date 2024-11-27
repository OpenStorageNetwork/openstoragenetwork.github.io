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


## Desktop applications

### Cyberduck (Windows, MacOS)

[Cyberduck](https://cyberduck.io/) is a popular graphical file transfer tool that supports the S3 API.
However, OSN requires a non-default S3 profile to connect to OSN. To enable the profile: 

1. Open the Cyberduck "Preferences" pane from the "Edit" menu dropdown.
2. Select "Profiles" and search for the **"S3 (Deprecated path style requests)"** profile.  
{{< figure src="cyberduck-deprecated-path-profile.png" alt="Selecting the bookmarks menu and adding new bookmark" >}}
3. Check the checkbox next to the **"S3 (Deprecated path style requests)"** profile to enable.

To add your OSN bucket and access credentials:

1.  Open Cyberduck and select the bookmarks icon
{{< figure src="cyberduck-new-connection.png" alt="Selecting the bookmarks menu and adding new bookmark" >}}
2.  Fill in the information corresponding with your OSN bucket.  
{{< figure src="cyberduck-bookmark-config.png" alt="Selecting the bookmarks menu and adding new bookmark" >}}  
    **Type:** S3 (Deprecated path style requests)  
    **Nickname:** A name for your bookmark (only visible to you)
    **Server:** your OSN bucket endpoint  
    **Access Key ID:** your OSN bucket access key  
    **Secret Access Key:** your OSN bucket access secret  
    **Path (under "More Options"):** your OSN bucket name prefixed with "/". For example: `/osn-docs-example-bucket`

{{< callout note >}}
When specifying the server, use the hostname portion of the endpoint
(i.e. if the location is `https://mghp.osn.mghpcc.org` the hostname is
`mghp.osn.mghpcc.org`).
{{< /callout >}}

If you are accessing an anonymous access bucket, use "anonymous" for the Access ID portion and
Cyberduck will then select the grayed out anonymous access box in the window.

{{< figure src="cyberduck-anonymous.png" alt="Using anonymous access as your user" >}}

Exit the window for the bookmark to save.

#### Browsing, Uploading, and Downloading

Once a bookmark is created, you can use it to access data by
double-clicking the bookmark. This logs you in and lists the
contents of the dataset.

{{< callout note >}}
If your buckets have large object counts, you will need to
increase the Timeout settings for connections.

Go to `Preferences > Connection` and change the box next to Timeout for
opening connections (seconds) and change the setting to 90 seconds.
{{< /callout >}}

{{< figure src="cyberduck-success.png" caption="Directory listing within bucket." >}}


Cyberduck client is a full-fledged transfer client so desktop
up/downloads can be easily performed for data sets. The tool supports multiple upload/download streams, chunking, pausing
and restarting.

### Rclone

[Rclone](https://rclone.org/) is a CLI program to manage files on cloud
storage. It\'s similar to rsync but provides many additional features
including support for over [40 cloud storage
products](https://rclone.org/#providers).

#### macOS installation

##### Install Rclone via Homebrew

[Homebrew](https://brew.sh/) is a 3rd party package manager for macOS
that can be used to easily install many FOSS packages. To install
Homebrew, please see the documentation on their
[website](https://brew.sh).

Once Homebrew is installed, install rclone by running the following
command:

```bash
brew install rclone
```

##### Install Rclone without Homebrew

Alternatively, you can install rclone for macOS by running the
rclone-provided install.sh script which will download the relevant
precompiled binary.

    $ sudo -v ; curl https://rclone.org/install.sh | sudo bash

#### Linux installation

Installation of rclone for Linux can be done using your Linux
distribution specific package manager, or by using the rclone-provided
binary installer.

Note, if you are on a system where you do not have administrative
privledges, see the last section of the Linux installation documentation
on non-privledged installation.

##### Install Rclone using Linux package managers (requires root access)

For RedHat or RedHat clone distros:

    $ sudo dnf install rclone

For Debian-based distros including Ubuntu:

    $ sudo apt install rclone

For Arch-based distros:

    $ sudo pacman -S rclone

##### Install Rclone binary directly (requires root access)

Alternatively, you can install rclone for Linux by running the
rclone-provided install.sh script which will download the relevant
precompiled binary.

    $ sudo -v ; curl https://rclone.org/install.sh | sudo bash

##### Non-privledged installation of Rclone on Linux

If you are on an HPC system, first check to see if rclone is already
installed. For instance, if you are on a module-based system, you might
search for the rclone module.

```bash
module spider rclone
```

If it is available, then you can `module load rclone` and then follow
the rest of this documentation.

If rclone is not available on your HPC system, you can install it into
your `$HOME` directory. First, fetch and unzip the precompiled rclone
binary.

```bash
curl -O https://downloads.rclone.org/rclone-current-linux-amd64.zip
unzip rclone-current-linux-amd64.zip
cd rclone-*-linux-amd64
```

Place it in a directory that you have write access to and is in your
\$PATH. If one is not available, you can create one.

    $ mkdir $HOME/bin
    $ cp rclone $HOME/bin
    $ export PATH=$PATH:$HOME/bin
    $ echo export PATH=\$PATH:$HOME/bin >> ~/.bashrc

*Note: The export and echo commands are for bash and other
bourne-compatible shells.*

#### Windows installation

For Windows installtion, download the correct binary for your system. If
you are not sure, use the first download.

-   [Intel/AMD - 64
    Bit](https://downloads.rclone.org/rclone-current-linux-amd64.zip)
-   [Intel/AMD - 32
    Bit](https://downloads.rclone.org/rclone-current-linux-386.zip)
-   [ARM - 64
    Bit](https://downloads.rclone.org/rclone-current-linux-arm64.zip)

Once downloaded, open the file in Explorer and extract **rclone.exe**.
Rclone.exe is a portable binary and you can place it anywhere that is
convenient to call from CMD or powershell.

#### Rclone Configuration

The most straightforward way to configure Rclone for OSN is to edit the
rclone configuration file. This file may be found by typing the command
\"rclone config file\". The command will return the path to the rclone
config file. Open this file with a text editor and add the following
stanza to the end of the file: :

    [<alias>]
    type = s3
    provider = Ceph
    access_key_id = <access key>
    secret_access_key =<secret key>
    endpoint = <location> 
    no_check_bucket = true

Where: \* \<alias\> -- nickname of your choice for the allocation \*
\<access key\> -- the access key from the data manager or from the
portal \* \<secret key\> -- the secret key from the data manager of the
portal \* \<location\> -- the URL provided by the data manager or portal
without the bucket

An example of a configuration stanza might look like: :

    [ocean-data]
    type = s3
    provider = Ceph
    access_key_id = ASasd8KJHDAKH**&asd
    secret_access_key =asd(*&Adskj*(*(&868778
    endpoint = https://mghp.osn.xsede.org
    no_check_bucket = true

#### Rclone Commands

Rclone commands are of the form: :

    $ rclone command alias:/bucket

So, using the example config file entry described above and assuming a
bucket named \"phytoplankton\", one would list the content of the bucket
using the following command: :

    $ rclone ls ocean-data:/phytoplankton

You could copy a local file to the bucket with the command: :

    $ rclone copy my-local-file.dat ocean-data:/phytoplankton

Rclone offers a wide range of commands for performing typical unix file
operations (ls, cp, rm, rsync, etc.). Details on these commands can be
found on the [RCLONE documentation page](https://rclone.org/docs/).

### AWS CLI with OSN

Install the AWS CLI utility:

[Official instructions to
install](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
the lastest AWS command line interface

After installing the AWS CLI, create a "config" file, `~/.aws/config`,
with

    [yourprofilename]
    output=json

and add a corresponding credentials entry in your "credentials" file,
`~/.aws/credentials`, with

    [yourprofilename]
    aws_secret_access_key = your_secret_key
    aws_access_key_id = your_access_key

Your profile name is the one listed on the OSN storage page, with
project ID+name. For example:

    XYZ123415_Bob_Smith

After loading your `aws-cli` environment, you can use s3 commands such
as:

    aws s3 ls <yourbucket> --profile <yourprofilename> --endpoint <yourendpoint> --recursive --human-readable --summarize

Recall that if a bucket url is
<https://mghp.osn.xsede.org/phytoplankton>, then \<yourbucket\> is
phytoplankton, and \<yourendpoint\> is <https://mghp.osn.xsede.org>.

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
returned by the \"Find the Storage Gateway ID\" command.
