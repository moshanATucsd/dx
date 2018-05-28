<h1 class="title">$ tt do &lt;ID&gt; add &lt;volume or local filepath&gt;</h1>

#### Description

Adds a volume to a running deployment.

#### Parameters

| Flag, Name   | Description                              | Required |
| ------------ | ---------------------------------------- | -------- |
| `ID`         | Deployment ID displayed in `tt monitor`. | ✓        |
| `volume`     | Name of volume to add.                   | ✓        |

#### Usage
```bash
tt do 8620df57eb72 add myVolume
# or
tt do 8620df57eb72 add ~/Desktop/file.csv
```

#### Note

If a local filepath is referenced, `tt do add` will first upload your file or folder and then add it to the deployment.
