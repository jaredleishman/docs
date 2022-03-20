# Hosts (VMs)

Once we have the Infrastructure (Networking, Kubernetes cluster and other common configuration) and an environment (Tenant) setup, the next step is typically to launch EC2 VMs. These could be meant for

* EKS Worker Nodes
* Worker Nodes (Docker Host) if the built-in container orchestration is used.
* Regular nodes not part of any container orchestration, where a user maybe manually connecting and installing apps. Use cases for this is say using MSFT SQL in a VM, Running an IIS application etc.

![](<../../.gitbook/assets/image (17).png>)

While all the lower level details like IAM, role, SG, etc is abstracted away from the user (as they are derived from the Tenant), standard application centric inputs are required to be given. This includes a Name, Instance size, Availability Zone choice, Disk etc, Image ID etc. Most are optional, some are published as a list of user friendly choices by the admin in the plan (Image or AMI ID is one such example). Other than these AWS centric parameter There is one DuploCloud platform specific value to be given

**Agent Platform**: This is applicable if the VM is going to be used as a host for [container orchestration](../container-orchestration.md) by the platform. The choices are:

* EKS Linux: If this is to be added to EKS cluster i.e. EKS is the chosen approach for container orchestration
* Linux Docker: If this is to be used for hosting Linux containers using the [Builtin Container orchestration](../container-orchestration.md)      &#x20;
* Docker Windows: If this is to be used for hosting Windows containers using the [Builtin Container orchestration](../container-orchestration.md)
* None: If the VM is going to be used for non Container Orchestration purposes and contents inside the VM will be self-managed by the user

{% hint style="info" %}
If a VM is being used for container orchestration make sure that the Image ID is that of an corresponding to an Image for that container orchestration. This should be already setup for you and the drop down will have self descriptive Image IDs for example "EKS Worker",, "Duplo-Docker", "Windows Docker" etc. Anything that starts with Duplo would be an image for the Built-in container orchestration &#x20;
{% endhint %}

Several other functionalities around managing VMs is under the [Virtual Machines](../aws-services/virtual-machines/) sections and much of it is self descriptive in the DuploCloud UI.