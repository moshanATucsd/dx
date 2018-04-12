<h1 class="title">$ tt import &lt;repository name or url&gt; [parameters]</h1>

#### Description
Imports a public DockerHub image, or a file from a URL, or a shared DX volume or image to your account.

There are two types of imports: external and internal.
- External imports come from the internet into DX, such as from DockerHub or a URL.
- Internal imports come from other organization's with DX accounts.

When importing DockerHub images or files from a URL, it may take a few minutes to complete depending on the size of the image or file. DX supports imports up to 30 GB in size. When the import is complete, the size of the image or volume you imported will show.

You can also import volumes or images shared by other Tenzar DX organizations. These type of imports create a new copy of the volumes or images shared. Once imported, the volume or image belongs to your organization and cannot be modified or deleted by the organization that shared it.


#### Parameters
| Flag, Name | Description | Required |
|---------|-------------|-------------|
| `repository or url`  | Name of DockerHub repository, or URL.	     |  ✓ |
| `-n, --name` | Renames the image or file upon importing.	     |  - |
| `-i, --image` | Flag to import an image from a URL. | - |


#### Usage
```bash
tt import tensorflow/tensorflow
# or
tt import tensorflow/tensorflow:1.0
# or
tt import tensorflow/tensorflow:1.0 --name tf-image
# or
tt import https://www.files.com/myFile.csv
# or
tt import --image https://www.images.com/myImage.tar
# or
tt import dx.tenzar.com/s/65j7dcywj8g0sd0r
# or
tt import --image dx.tenzar.com/s/65j7dcywj8g0sd0r
```

#### Note
If the name of your import exceeds 25 letters, contains spaces, or illegal characters use `--name` to rename it.
