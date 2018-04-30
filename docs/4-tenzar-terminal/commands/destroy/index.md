<h1 class="title">$ tt destroy &lt;ID&gt;</h1>

#### Description
Terminates and wipes a running instance.

Deployments are ephemeral. By 'ephemeral' we mean that the mounted volumes, memory, active processes, etc., within the instances are wiped when destroyed. Destroying a deployment does not delete the actual volume(s) or image stored in DX, only the copy used in the deployment. In order to save files that you do not want destroyed when running `tt destroy`, use `tt save` to save a file or folder in the `/tenzar_volumes` folder back to DX.



#### Parameters
| Flag, Name | Description | Required |
|---------|-------------|-------------|
| `ID`  | Deployment ID displayed in `tt monitor`.	     |  ✓ |

#### Usage
```bash
tt destroy 8620df57eb72
```

#### Note
Exiting an instance does not destroy the instance. You can re-connect to a running instance by running `tt connect` again. Use `tt destroy` to terminate a running instance and stop billing.

You pay as you go for the amount of time you have an instance `Running`. Compute billing is calculated from the time you click `ENTER` to deploy, until you `tt destroy` your deployment. To avoid unnecessary charges, destroy your deployments when you are done using them.
