<p style="background:#fffbe6"><b>Warning: </b>This command will be deprecated in version <i>3.6.2</i>. Please use <code>tt do save</code>.</p>

<h1 class="title">$ tt save &lt;ID&gt; &lt;filename in tenzar_volumes&gt; [parameters]</h1>

#### Description

Saves a file or folder in an instance's `/tenzar_volumes` directory back to DX.

Because deployments are ephemeral and are wiped when destroyed, use `tt save` to save new or modified files or folders in a running instance back to your DX volumes.

#### Parameters

| Flag, Name        | Description                                    | Required |
| ----------------- | ---------------------------------------------- | -------- |
| `ID`              | Deployment ID displayed in `tt monitor`.       | ✓        |
| `remote filepath` | name of file or folder in `/tenzar_volumes`\*. | ✓        |
| `-n, --name`      | Renames file or folder upon saving.            | -        |

> You do not need to specify a full absolute path. The save command will only look in your `/tenzar_volumes` directory, so you can use the name or relative file path.

#### Usage

```bash
tt save 8620df57eb72 myFile.txt
# or
tt save 8620df57eb72 myFolder
# or
tt save 8620df57eb72 myFolder --name newFolder
# or
tt save 8620df57eb72 myFolder -n newFolder
```

#### Note

When you deploy an instance with volumes, DX creates copies of your volumes in that instance and puts them in `/tenzar_volumes` directory. Any modifications to those volumes or newly created files within the instance are discared when you destroy your instance unless you save them back to DX.

Only files and folders located in the `/tenzar_volumes` directory can be saved.

If you are saving large files, it may take some time to complete. So do not destroy your instance until the save is finished — you can see the progress with `tt volumes`. If you do choose to destroy your instance while the save is in progress, your changes will not be saved.
