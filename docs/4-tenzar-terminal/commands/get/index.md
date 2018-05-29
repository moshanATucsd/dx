<p style="background:#fffbe6"><b>Warning: </b>This command will be deprecated in version <i>3.6.2</i>. Please use <code>tt do get</code>.</p>

<h1 class="title">$ tt get &lt;ID&gt; &lt;remote filepath&gt; [local folderpath]</h1>

#### Description

Fetches a file from a running deployment and inserts it in your local computer.

By default, the file is placed in your `Downloads` folder. Optionally, you can specify an alternate folder location in your computer to place the file. The folder destination must exist in your computer.

#### Parameters

| Flag, Name         | Description                                            | Required |
| ------------------ | ------------------------------------------------------ | -------- |
| `ID`               | Deployment ID displayed in `tt monitor`.               | ✓        |
| `remote filepath`  | Location of file in instance.                          | ✓        |
| `local folderpath` | Destination folder in your computer to place the file. | ✓        |

#### Usage

```bash
tt get 8620df57eb72 ~/myFile.txt
# or
tt get 8620df57eb72 ~/myFile.txt ~/Desktop/
```

#### Note

When specifying a destination folder, make sure to include a `/` at the end of the folder name.

This command can only be used with small files less than 10 MBs in size. It should only be used if you are missing a file or need to change a file in your deployment. For all other file transfers, use the Tenzar Terminal more robust `tt save` and `tt download` command to save and download your files and folders.
