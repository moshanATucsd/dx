<h1 class="title">$ tt do &lt;ID&gt; remove &lt;filename in tenzar_volumes&gt;</h1>

#### Description

Removes a file or folder from the `/tenzar_volumes` directory in a running deployment.

#### Parameters

| Flag, Name | Description                              | Required |
| ---------- | ---------------------------------------- | -------- |
| `ID`       | Deployment ID displayed in `tt monitor`. | ✓        |
| `filename` | Name of file or folder to remove.        | ✓        |

#### Usage

```bash
tt do 8620df57eb72 remove myFolder
# or
tt do 8620df57eb72 remove file.csv
```
