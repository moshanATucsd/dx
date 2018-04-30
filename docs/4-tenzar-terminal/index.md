### Tenzar Terminal (Command Line Interface)

#### Installing

Click [here](https://dx.tenzar.com/install) to download and install the Tenzar Terminal or visit the [installation page](/docs/cli/install).

#### Syntax

All commands in the Tenzar Terminal have the following structure:

<img src="https://s3.amazonaws.com/assets.tenzar.com/docs/command-syntax.png" alt="Tenzar Terminal Syntax" width="100%" style="border-radius: 3px; margin-bottom: 20px">

* Angle brackets `< >` indicate required parameters.
* Square brackets `[ ]` indicate optional parameters.
* Single dash `-` indicates shorthand options.
* Double dashes `--` indicate long form options.

#### Minimum Required Usage

Some functionalities in DX are only available through the Tenzar Terminal, such as uploads, downloads, and connections. If you are not comfortable with a command line interface, don't worry; Tenzar Terminal's syntax is simple, short, and easy to adopt. For most other functionalities, you can choose to use the Dashboard.

##### Actions only available from the Tenzar Terminal:

* upload
* download
* connect
* save
* get
* put

#### Usage 101: Tenzar Terminal

The following examples teaches you how to use only the most basic commands of the Tenzar Terminal on macOS or Linux computers. For more advanced usage visit the [tutorials](/docs/tutorials) section.

###### Login

To begin using the Tenzar Terminal, log into your organization with your username and password.
If you have installed the macOS version, you can login by clicking on the Tenzar octopus in the top menu bar:

<center>
<img src="https://s3.amazonaws.com/assets.tenzar.com/docs/login-app.png" alt="Tenzar App Login" width="350px" style="border-radius: 3px; margin-bottom: 20px">
</center>

Or open your terminal and type `tt login`

```bash
$ tt login

Organization ID: octo-org
Username: octo
Password:
Login successful.
```

> Note: your password will be hidden as you type.

Once you are logged in, you can get a feel of the Terminal by running some simple commands to view your volumes, images, and deployments.

To list all of your team's volumes:

```bash
tt volumes
```

To list all of your team's images:

```bash
tt images
```

To list your deployments:

```bash
tt monitor
```

If you are new to DX, you will see empty lists for all of the above.

###### Upload

To upload a file or folder from your computer simply type `tt upload` followed by the full path of the file or folder:

```bash
tt upload /Users/octo/Desktop/myFile.dat
```

On macOS, you can also drag and drop your file or folder into the terminal:

<img src="https://s3.amazonaws.com/assets.tenzar.com/docs/drag-upload.png" alt="tt-upload" width="350px" style="border-radius: 3px; margin-bottom: 20px">

> Note: the name of your file or folder cannot contain spaces.

###### Connect

To connect to a running deployment simply type `tt connect`.

```bash
tt connect
```

If you have more than one running deployment, then type `tt monitor` to view the Deployment ID, and then use this ID to connect to your instance.

Visit the command documentation or the complete [Tenzar Terminal tutorial](/docs/tutorials/tenzar-terminal) for additional usage.
