<h1 class="title">$ tt upload &lt;filepath&gt; [parameters]</h1>

#### Description

Uploads a file, folder, or image into your organization.

By default, all files and folders are uploaded as volumes. To upload an image, use the `--image` or shorthand `-i` parameter. Only `.tar` image files are allowed.

#### Parameters

| Flag, Name    | Description                                          | Required |
| ------------- | ---------------------------------------------------- | -------- |
| `filepath`    | Path of folder or file in local computer.            | ✓        |
| `-n, --name`  | Renames file, folder, or image upon uploading.       | -        |
| `-i, --image` | Uploads a Docker image .tar file as Tenzar DX image. | -        |

#### Usage

```bash
tt upload ~/Desktop/data.csv
# or
tt upload ~/Desktop/dataFolder
# or
tt upload data.csv
# or
tt upload data.csv -n newName.csv
# or
tt upload -i datascience_image.tar
# or
tt upload --image datascience_image.tar --name newImageName.tar
```

#### Note

If the name of your upload exceeds 25 letters, contains spaces, or illegal characters use `--name` to rename it.
