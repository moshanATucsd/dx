<div align="center">
  <img src="https://assets.tenzar.com/web/black-octo.png" height="300" alt="Tenzar DX">
</div>

# Tenzar DX

#### Visit the latest Tenzar DX Docs at: [tenzar.com/docs](https://www.tenzar.com/docs)

---
### Contributing to the DX Documentation

If you'd like to improve our documentation please follow the contributing guidelines for prioritizing changes.

##### To make changes to the documentation do the following:
1. Click on the Fork button in Github near the top right corner to create a copy of the dx repository in your Github account.

2. Make your edits and commit them to your "forked" copy.

3. When you are ready to tell us about your changes, click New Pull Request in the official DX repository.

4. That's it!

We will review your changes and if they are valuable, we will add them to the official DX docs.

##### Documentation Contributing Guidelines:
1) Accurate: Does the existing documentation contain errors? </br>
2) Current: Is the existing documentation outdated? </br>
3) Clear: Is the existing documentation well explained and documented?


If you encounter errors or bugs throughout your usage, please contact us directly or open an issue. See our [responsible disclosure guidelines](#disclosure).

---
### Welcome to Tenzar DX.
DX is a seamless high-performance computing platform for data scientists, researchers, IT admins, and developers.
Use DX if you are looking to launch computations or workloads to the cloud, share data instantly with other teams, and store an unlimited number of private Docker images ready for use. DX is a multi-purpose, language-agnostic, computing platform capable of running small and terabyte scale workloads.

Enterprise and teams use DX as their computing platform to store data, collaborate, and run computing workloads. The most common uses are for:

- Machine Learning
- Bioinformatics
- Data Science
- Scientific Computing
- Data and Compute Collaboration

You can use DX from the [web Dashboard](https://dx.tenzar.com) or from the Tenzar Terminal desktop application.


### Tenzar Terminal
<img src="https://assets.tenzar.com/app/img-tenzar-app.png" alt="Tenzar Terminal tt" height="100">

### How to use it - Hello World:

DX enables you to deploy an instance in the cloud with a Docker image and any of your files (collectively "a computation") with a single flexible command: ``tt deploy --type c4 --image tensorflow datasets code``

This command does the following:
- Deploys a `c4` instance with 16 CPUs and 30 GB of memory
- Starts your Docker image as container in the instance
- Transfers your `datasets` and `code` folders into the container

You then have full admin/root access to this container via SSH: `tt connect`

This command automatically connects you to your running container. Once connected, you have full control of your container to run any workload at `c4` scale (16 CPUs and 30 GB of memory), with your files and data readily available within it.


To learn more about how to use Tenzar DX, visit [tenzar.com](https://www.tenzar.com)

-----
### Getting Started

- Create your account at [tenzar.com](https://www.tenzar.com)
- Install the Tenzar Terminal app from [here](https://dx.tenzar.com/install) and login
- Import your data into DX from a URL or upload it directly from a computer:
  ``$ tt upload /Users/octo/myData``
- Import a Docker image directly from DockerHub:
  ``$ tt import tensorflow/tensorflow``
- Launch your Deployment:
  ``$ tt deploy -i tensorflow myData``
- Connect to your Instance:
  ``$ tt connect``
- Within the instance, find your data at `/tenzar_volumes`
- Run your workload.

You can invite other members to your account, or share data with other organizations with just a link.

------
### <a name="disclosure"></a> Security and Privacy
Tenzar recognizes the importance of security and privacy for data and computations. We encourage responsible disclosure of security vulnerabilities by contacting Tenzar at <b>security@tenzar.com</b>.

##### Responsible Disclosure Guideline:

1) Notify us of any security vulnerability at <b>security@tenzar.com</b>. <br/>
2) Provide us a reasonable amount of time to fix the issue before disclosing it elsewhere. <br/>
3) Make a no less than reasonable, conscious, good-faith, effort to not leak or destroy any information, affect software operations, or cause damage to other accounts.

##### Rewards

The minimum payout is $50 USD and an entry in our hall of fame for reporting a new security vulnerability which results in a code or configuration change on our part. There is no maximum reward, and we may award higher amounts based on the severity or creativity of the vulnerability found.
