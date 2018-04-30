### Tenzar Terminal Commands

<br/>

| COMMAND | DESCRIPTION |
|----------|-------------|
| login| Logs your account into your organization. |
| logout | Logs your account out of your organization. |
| upload| Uploads a file, folder, or image into your organization. |
| download| Downloads a volume to a local computer. |
| import| Imports a public DockerHub image, or a file from a URL, or a shared DX volume or image to your organization. |
| images| Displays a list of all imported or uploaded images and pending imports in your organization. |
| volumes| Displays a list of all uploaded or imported volumes in your organization. |
| deploy| Launches a virtual machine instance with the specified parameters, such as volume(s), image, instance type, and extra storage. |
| monitor| Displays a list of your active and most recently stopped deployments. |
| connect| Connects your local computer to a running instance via SSH. |
| put| Inserts a small sized file from your computer into a running instance. |
| get| Fetches a file from a running deployment and inserts it in your local computer. |
| save| Saves a file or folder in an instance's */tenzar_volumes* directory back to DX. |
| destroy| Terminates and wipes a running instance. |
| share| Creates a link to share a volume or image with other DX organizations. |
| delete| Moves to the trash a volume or image from your DX organization. |



#### Usage

```text
Usage:

	tt login
	tt logout
	tt upload <local filepath> [-i] [-n name]
	tt download <volume> [local destination]
	tt import <repository name or url> [-i] [-n name]
	tt images
	tt volumes
	tt deploy [-i image] [-t type] [-s space] [volume(s)]
	tt monitor
	tt connect <ID>
	tt put <ID> <local filepath> [remote destination]
	tt get <ID> <remote filepath> [local destination]
	tt save <ID> <filename in tenzar_volumes> [-n name]
	tt destroy <ID>
	tt share <image or volume> [-i]
	tt delete <image or volume> [-i]
```
