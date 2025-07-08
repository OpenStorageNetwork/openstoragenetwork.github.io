---
title: Restic
---

[Restic](https://restic.readthedocs.io/) is a backup utility that can use an S3 bucket as a remote backup storage server. To use, you install Restic on the system you'd like to back up, configure to use your OSN S3 bucket, specify the files for backup, and either run the backup script manually or on a schedule.

Restic provides [general documentation for interacting with S3 buckets](https://restic.readthedocs.io/en/stable/030_preparing_a_new_repo.html#s3-compatible-storage). This documentation page is specific to OSN S3 buckets.

## Installation 

Restic provides [installation options through various package managers](https://restic.readthedocs.io/en/stable/020_installation.html) for Linux, MacOS, and Windows. If you want to use Restic on a compute cluster which does not provide it, you can download [standalone binary releases](https://github.com/restic/restic/releases/latest), which don't require administration privileges to install.

## Configuration

Restic configuration for your OSN credentials is the same as in the [OSN AWS CLI documentation]({{< relref "aws-cli" >}}). You can use either the configuration file method or the environment variable method.

## Initialization

After configuring your bucket credentials, initialize the Restic backup: 

```
restic -r s3:https://<your bucket endpoint>/<your bucket name>/<optional sub-path>

# example
```
{{< callout note >}}
Unfortunately, Restic can't understand the endpoint setting from the AWS config files. You need to include the full URL in the repository path. 
{{< /callout >}}

{{< callout warning >}}
The bucket or sub-path you direct Restic to initialize must be empty.
{{< /callout >}}
