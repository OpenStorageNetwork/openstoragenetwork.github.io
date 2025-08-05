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
restic -r s3:https://<your bucket endpoint>/<your bucket name>/<optional sub-path> init

# example
# restic -r s3:https://uma1.osn.mghpcc.org/osn-docs-example-bucket/restic-example init
```
{{< callout note >}}
Unfortunately, Restic can't understand the endpoint setting from the AWS config files. You need to include the full URL in the repository path. 
{{< /callout >}}

{{< callout warning >}}
The bucket or sub-path you direct Restic to initialize must be empty.
{{< /callout >}}

The `init` command will prompt you to set a password for the backup repository. This is the encryption key for your backups. Keep it securely stored because there is no way to recover it if lost.

## Backing up data

To back up a directory to your new Restic repository, run: 

```
restic -r s3:https://<your bucket endpoint>/<your bucket name>/<optional sub-path> --verbose backup <directory to backup>

# example
# restic -r s3:https://uma1.osn.mghpcc.org/osn-docs-example-bucket/restic-example --verbose backup ~/backup-test
```

For a full discussion on Restic backup options, see [the Restic documentation](https://restic.readthedocs.io/en/latest/040_backup.html).

## Saving credentials

To use Restic in an automated way (for example, [on a schedule]({{< relref "#setting-a-backup-schedule" >}})), you need to supply your Restic and S3 credentials in an automated way. For saving your OSN S3 credentials to AWS credential files, see the [OSN and AWS S3 CLI documentation]({{< relref "aws-cli#configuration-files" >}}). To save your Restic password and repository location, you can use environment variables or save them to files. 

{{< callout warning >}}
This method saves your credentials to plain text. Ensure you're on a trusted system before using this method. If you're using Restic in a shared cluster environment, these credentials will be accessible by the systems administration team.
{{< /callout >}}

Restic understands `RESTIC_REPOSITORY` and `RESTIC_PASSWORD` to retrieve the repository and backup password. You can set these environment variables in a location that is automatically sources, such as your `~/.bashrc`, as part of a backup script, or in a file to source manually ahead of the backup. For example, in a bash shell, you can save the following file to `run_restic_backup.sh`:

```
#!/bin/bash

RESTIC_REPOSITORY="s3:https://<your bucket endpoint>/<your bucket name>/<optional sub-path>"
RESTIC_PASSWORD="<your restic password>"

restic --verbose backup <directory to backup>
```

Then, to run your backup, execute the script with `bash run_restic_backup.sh`.

## Setting a backup schedule

Restic works well with workload schedulers like `cron` for Linux, `Task Scheduler` for Windows, and `scrontab` on Slurm systems. The following examples all schedule a backup for 2 am system time, using the `run_restic_backup.sh` defined in the [saving credentials section]({{< relref "#saving-credentials" >}}):

### Cron example

[Cron is a Linux utility](https://man7.org/linux/man-pages/man8/cron.8.html) for scheduling repeated work. To edit your cron file, run the command `crontab -e`, then enter your cron job setting on a new line: 

```
0 2 * * * bash ~/run_restic_backup.sh
```


### Slurm system using `scrontab` example

[Slurm systems use `scrontab`](https://slurm.schedmd.com/scrontab.html) to schedule repeated jobs. This is helpful since it doesn't require login nodes to be stateful and it moves your backup job onto a compute node. To edit your `scrontab` file, run the command `scrontab -e`, then enter your scontab job settings: 

```
#SCRON --job-name=RunBackup
#SCRON --time=1:00:00
0 2 * * * bash ~/run_restic_backup.sh
```

{{< callout note >}}
The `#SCRON` prefix is equivalent to `#SBATCH` in Slurm batch files. You can set many standard Slurm settings here, such as `partition`, `mem`, and `cpus-per-task`. What you need to set depends on your particular cluster. 
{{< /callout >}}

## Restoring from backup

A backup is only as good as your ability to retrieve it. **You should test your ability to retrieve a backup before relying on it!** Verify you can get a backup back *before* you need it. To restore the `latest` snapshot from Restic, run:

```
restic -r s3:https://<your bucket endpoint>/<your bucket name>/<optional sub-path> --verbose restore --target <directory to restore to> latest

# example 
restic -r s3:https://uma1.osn.mghpcc.org/osn-docs-example-bucket/restic-example --verbose restore --target /tmp/restic-restore latest
```

For more information on restoring Restic snapshots, see the [Restic restoration documentation](https://restic.readthedocs.io/en/latest/050_restore.html).
