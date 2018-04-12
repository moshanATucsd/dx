<h1 class="title">$ tt connect &lt;ID&gt;</h1>

#### Description
Connects your local computer to a running instance via SSH.

Use the `Deployment ID` to connect to a running instance. To exit from a running instance, type `exit` or `Ctrl+D`.


#### Parameters
| Flag, Name | Description | Required |
|---------|-------------|-------------|
| `ID`  | Deployment ID displayed in `tt monitor`.	     |  ✓ |

#### Usage
```bash
tt connect 8620df57eb72
```

#### Note
To create more than one active connection to the instance, you can open a new terminal window and run `tt connect`.

Exiting an instance does not destroy the instance. You can re-connect to a running instance by running `tt connect` again. Use `tt destroy` to terminate an instance.
