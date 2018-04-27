### Volumes

Volumes are how data is stored on DX. A volume simply contains the files and folders you upload or import.

#### Why Volumes?
DX stores your data under the concept of a Volume. Volumes are nothing more than a file or folder stored on DX -- except we call them "Volumes". However, unlike a folder in your computer that you can browse and expand, DX treats your volumes as a singular unit. Packaging your files or folders under a single unit and simplifies the syntax and makes interacting with your data in DX faster and easier.

Wrapping your files and folders as Volumes streamlines collaboration, allowing you to easily reference a single item to run your workloads as opposed to a variety of namespaces or file paths. For example, deploying a volume to an instance is as easy as: `tt deploy myVolume`, or to include more volumes: `tt deploy myVolume1 myVolume2 myVolume3`.

To share volumes, you can create a sharing link from the dashboard or use the terminal: `tt share myVolume`.

DX can handle volumes from zero to 1 TB (one terabyte) in size. You can easily upload files and folders through the Tenzar Terminal's `upload` command. For example `tt upload somefolder`. It's as easy as specifying the path of the file or folder you want to upload or simply dragging-and-dropping it into your terminal.

#### Volume Advantages
DX implements [binary diffs](https://en.wikipedia.org/wiki/Diff_utility) on the fly to automatically transfer just the data you need. That means that if you modify a single file within your 1 TB folder, re-uploading to DX will not transfer 1 TB again. This DX native feature outperforms most traditional methods of transferring data between computers and enables faster deployments and uploads.
