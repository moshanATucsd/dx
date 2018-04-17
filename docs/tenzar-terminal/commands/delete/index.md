<h1 class="title">$ tt delete &lt;volume or image&gt; [-i]</h1>

#### Description
Moves to the trash a volume or image from your DX organization.

Volumes and images in the trash have 30 days until they are automatically erased. During the 30 days, you have the ability to recover or empty your trash items from the [trash dashboard](https://dx.tenzar.com/trash).  

#### Parameters
| Flag, Name | Description | Required |
|---------|-------------|-------------|
| `volume or image`  | Name of volume or image to delete	.	     |  ✓ |
| `-i, --image`  | Flag to delete an image.	     |  - |

#### Usage
```bash
tt delete myVolume
# or
tt delete --image myImage
# or
tt delete -i myImage
```
