<p style="background:#fffbe6"><b>Warning: </b>This command will be deprecated in version <i>3.6.2</i>. Please use <code>tt do put</code>.</p>

<h1 class="title">$ tt put &lt;ID&gt; &lt;local filepath&gt; [remote folderpath]</h1>

#### Description

Inserts a small sized file from your computer into a running instance.

By default, the file is placed in the home directory. Optionally, you can specify an alternate folder location within the instance to place the file. The folder destination must exist within the instance.

#### Parameters

| Flag, Name          | Description                                       | Required |
| ------------------- | ------------------------------------------------- | -------- |
| `ID`                | Deployment ID displayed in `tt monitor`.          | ✓        |
| `local filepath`    | Location of file in local computer.               | ✓        |
| `remote folderpath` | Destination folder in instance to place the file. | ✓        |

#### Usage

```bash
tt put 8620df57eb72 myFile.txt
# or
tt put 8620df57eb72 ~/Desktop/myFile.txt
# or
tt put 8620df57eb72 ~/Desktop/myFile.txt /targetFolder/
```

#### Note

When specifying a destination folder, make sure to include a `/` at the end of the folder name.

This command can only be used with small files less than 10 MBs in size. It should only be used if you are missing a file or need to change a file in your deployment. For all other file transfers, use the Tenzar Terminal more robust `tt upload` command to upload your files and folders.
