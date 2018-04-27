### Volumes

#### What are Volumes
Volumes are how data and files are stored on DX. A volume simply contains the files and folders you upload or import.

#### Why Volumes
DX stores your data under the concept of a Volume. Volumes are nothing more than a file or folder stored on DX--except we call them "Volumes". However, unlike a folder in your computer that you can browse and expand, DX treats your volumes as a singular unit. Packaging your files or folders under a single unit and simplifying the syntax, makes interacting with your data in DX much easier and faster.

Wrapping your folders and files as Volumes streamlines collaboration within your team and with others as you can always easily reference a single item to run your workloads as opposed to a variety of namespaces or file paths. For example, deploying a volume to an instance is as easy as: `tt deploy myVolume`, or to include more volumes: `tt deploy myVolume1 myVolume2 myVolume3`.

Similarly, to share volumes with others: `tt share myVolume`.

DX can handle volumes of zero size up to volumes of 1 TB (one terabyte) in size. You can easily upload files and folders through the Tenzar Terminal's `upload` command. For example `tt upload somefolder`. It's as easy as specifying the path of the file or folder you want to upload or simply dragging-and-dropping it into your terminal.

#### Volume Advantages
DX implements [binary diffs](https://en.wikipedia.org/wiki/Diff_utility) on the fly to automatically transfer just the data you need. That means that if you modify a single file within your 1 TB folder, re-uploading to DX will not re-upload 2 TBs again. This DX native feature outperforms most traditional ways of transferring data between computers and leads to quicker deployments and uploads.
