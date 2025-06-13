---
title: Rclone
---

[Rclone](https://rclone.org/) is a CLI program to manage files on cloud
storage. It's similar to rsync but provides many additional features
including support for over [40 cloud storage
products](https://rclone.org/#providers). To install Rclone, [choose the download appropriate for your operating system](https://rclone.org/downloads/).


## Rclone + OSN Configuration

The most straightforward way to configure Rclone for OSN is to edit the
rclone configuration file. This file may be found by typing the command
\"rclone config file\". The command will return the path to the rclone
config file. Open this file with a text editor and add the following
stanza to the end of the file: :

```conf
[<alias>]
type = s3
provider = Ceph
access_key_id = <access key>
secret_access_key = <secret key>
endpoint = <endpoint> 
no_check_bucket = true
```

Where: 
- `<alias>`: the nickname of your choice for the allocation 
- `<access key>`: the access key from the data manager or from the
portal 
- `<secret key>`: the secret key from the data manager of the
portal 
- `<endpoint>`: the URL provided by the data manager or portal
without the bucket

For example:

```conf
[ocean-data]
type = s3
provider = Ceph
access_key_id = ASasd8KJHDAKH**&asd
secret_access_key = asd(*&Adskj*(*(&868778
endpoint = https://mghp.osn.xsede.org
no_check_bucket = true
```

#### Rclone Commands

Rclone commands are of the form:

```
rclone command <alias>:/<bucket>
```

Using the example config file entry described above and assuming a
bucket named `phytoplankton`, the following command lists the content of the bucket:

```
rclone ls ocean-data:/phytoplankton
```

To copy copy a local file to the bucket, use the command:

```
rclone copy my-local-file.dat ocean-data:/phytoplankton
```


Rclone offers a wide range of commands for performing typical unix file
operations (`ls`, `cp`, `rm`, `rsync`, etc.). See a full list with usage information on the [Rclone documentation page](https://rclone.org/docs/).
