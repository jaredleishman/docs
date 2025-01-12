# Step 4: Create Host

{% hint style="info" %}
Make sure you have switch the Tenant drop down to the desired tenant i.e. dev01 in this case
{% endhint %}

## Steps for creating a host

Switch to dev01 tenant from the drop down at the top of the page.&#x20;

Then go to DevOps --> Hosts --> EC2 tab and Click on +Add. You will need to give the following inputs:

* Name: host01
* Agent Platform: EKS Linux
* Image ID: Make sure it is prefixed with **EKS-**&#x20;
* This is the image published by AWS for EKS worker for the version of Kubernetes deployed when we created the infra. If you don't see an image ID starting with EKS .. then look up the ami-id for the desired EKS version from the table here [https://docs.aws.amazon.com/eks/latest/userguide/eks-optimized-ami.html](https://docs.aws.amazon.com/eks/latest/userguide/eks-optimized-ami.html) If you are following this quick start guide then the region should be us-west-2 as that is where we created the infrastructure. Once you have the AMI ID then choose "Other" for the Image ID drop down and paste the ami-id. If you need assistance with Image ID ping in the DuploCloud Slack channel

The host should get launched and soon get registered with Kubernetes and should show in Connected state in the DuploCloud UI as shown below.

![](<../../../.gitbook/assets/image (51).png>)

