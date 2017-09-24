## Data Management ##

When users entering their Workspace of Jupyter Notebook, they will see
the tree of filesa and directories. Users can perform **Rename** and
**Delete** operating while selecting some files. 

Click **New** - **Folder** can create a folder. Click **New** - ** Text File
** can create a text file with name *untitled.txt*，and enter the [File Editing](edit.md) webpage.

Click **Upload**,  users can upload their data files to the Workspace.
For technical reasons, Broken-point Continuingly-transferring is not supported now. For
large data file, it is better to use server-server transfering method.
Users can open [Terminal](terminal.md), using `wget` or `curl` to
**download** from some HTTP server. This has an advantage: even if the
browser is closed, the downloading is still continuing in the background.
Therefore it is the recommended way of transfering large data files.

Using `wget`

```
$ wget -c http://192.168.4.5/download/data1.zip
```

Using `curl`

```
$ curl -O http://192.168.4.5/download/data1.zip
```

**Note**:  The `~/nfs` directory is the [Dataspace](../concepts/nfs.md). The files in Dataspace will be shared among all containers in the vcluster, and are persistent. Files in other directory are all transient, will be destroyed when the container is deleted.
