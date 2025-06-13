---
title: Cyberduck
---

[Cyberduck](https://cyberduck.io/) is a popular graphical file transfer tool for Windows and macOS that supports the S3 API.
However, OSN requires a non-default S3 profile to connect to OSN. To enable the profile: 

1. Open the Cyberduck "Preferences" pane from the "Edit" menu dropdown.
2. Select "Profiles" and search for the **"S3 (Deprecated path style requests)"** profile.  
{{< figure src="cyberduck-deprecated-path-profile.png" alt="Selecting the bookmarks menu and adding new bookmark" >}}
1. Check the checkbox next to the **"S3 (Deprecated path style requests)"** profile to enable.

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

## Browsing, Uploading, and Downloading

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