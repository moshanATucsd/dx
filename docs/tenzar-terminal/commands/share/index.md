<h1 class="title">$ tt share &lt;volume or image&gt; [-i]</h1>

#### Description
Creates a link to share your a volume or image with other DX organizations.

Use this command to share volume(s) or image(s) to one or more DX organizations. When another organization imports your shared volume or image, a copy is created in their account.


#### Parameters
| Flag, Name | Description | Required |
|---------|-------------|-------------|
| `volume or image`  | Name of volume or image to share.	     |  ✓ |
| `-i, --image` | Flag to share an image. | - |


#### Usage
```bash
tt share myVolume
# or
tt share -i myImage
```
