---
title: AWS CLI
---

Follow the [official instructions to
install](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
the latest AWS command line interface for your operating system. 
To access your OSN bucket, you can configure the AWS CLI using either configuration files or using environment variables. 

## Configuration files

Configuring the AWS CLI to use your OSN bucket requires two files: `~/.aws/config` and `~/.aws/credentials`.

### `~/.aws/config`

```
[profile <your_profile_name>]
output = json
endpoint_url = <your bucket endpoint>
request_checksum_calculation = when_required
response_checksum_validation = when_required
```

### `~/.aws/credentials`

Add a corresponding credentials entry in your "credentials" file,
`~/.aws/credentials`, with

```
[<your_profile_name>]
aws_secret_access_key = <your_secret_key>
aws_access_key_id = <your_access_key>
```

`your_profile_name` is an arbitrary name you choose to describe this configuration and credential set. For ease of use, don't use spaces in your profile name.  For example, `ocean-data`.

{{< callout warning >}}
Notice that the label is `[profile <your_profile_name>]` (with the word `profile` verbatim) in the config file, but only `[<your_profile_name>]` in the credentials file.
{{< /callout >}}

## Environment variables

At times it's easier to provide the CLI your credentials via environment variables. You can set all settings defined in the files described above this way. For example, in a Linux or macOS terminal: 

```bash
export AWS_ENDPOINT_URL=<endpoint>
export AWS_DEFAULT_OUTPUT=json
export AWS_REQUEST_CHECKSUM_CALCULATION=when_required
export AWS_RESPONSE_CHECKSUM_VALIDATION=when_required
export AWS_SECRET_ACCESS_KEY=<your secret key>
export AWS_ACCESS_KEY_ID=<your access key>
```

{{< callout note >}}
When setting variables in bash, do not add spaces on either side of `=`. For [Windows CMD and Powershell, see the AWS documentation](https://docs.aws.amazon.com/cli/v1/userguide/cli-configure-envvars.html).
{{< /callout >}}

## Using the CLI

Once you set up your configuration, [you can use the CLI to perform various file actions](https://docs.aws.amazon.com/cli/latest/userguide/cli_s3_code_examples.html), including

- **List all the files in your bucket**:
  ```
  aws s3 ls --profile <your_profile_name> --recursive <your bucket name>
  ```

- **Copy a local file to your bucket**:
  ```
  aws s3 cp --profile <your_profile_name> <local file> s3://<your bucket name>/
  ```
  To copy from OSN to your local machine, reverse the `<local file>` and `s3://<your bucket name>/` arguments

- **Copy a local directory to your bucket**
  ```
  aws s3 cp --profile <your_profile_name> --recursive \
  <your local directory> s3://osn-docs-example-bucket/<target directory name>/
  ```

{{< callout note >}}
AWS CLI commands that involve creating, modifying, or destroying the buckets themselves will not work with OSN.
{{< /callout >}}

