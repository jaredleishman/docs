# Docker web application

## Introduction <a href="#0-toc-title" id="0-toc-title"></a>

In this demo, we will deploy a simple Hello World NodeJS web app. DuploCloud pulls Docker images from Docker Hub. You can choose a public image or provide credentials to access your private repository. For the sake of this demo, we will use a ready-made image available on DuploCloud’s repository on Docker Hub.

1. Create a new host
2. Create a service
3. Create a load balancer

## Step 1: Create a new host <a href="#1-toc-title" id="1-toc-title"></a>

1. Login to your DuploCloud console.
2. Select “Deployments” from the tab on the top left corner.
3. Select “Hosts” from the tabs. Select “Azure” Cloud on the left-side Section. A Host is the instance in which your Docker container will run. You should choose a host with appropriate processing capacity for your application.
4. Click on the + icon to choose your host. Fill out the advanced configuration form if required and click submit.

![](https://duplocloud.com/wp-content/uploads/2021/11/N1-host1.png)

You should now see your Host present in the table. Please give it a moment to instantiate.

## Step 2: Create a service <a href="#2-toc-title" id="2-toc-title"></a>

1. Next, we can create a Service. A Service is nothing but a container with user specified image and environment variables. Let’s go ahead and click the + icon to create a new service.
2. Name the service “**test-service**“. For this demo we will use the latest, nodejs-hello image from Duplo’s public Docker hub repository. Fill in ‘`duplocloud/nodejs-hello:latest`‘ in the Docker Image field.
3. Enter the desired number of replicas you want in the swarm. Please note that each replica runs in an individual Host. The number of replicas must equal the number of Hosts. For the sake of this demo, we will choose 1.
4. Fill in the desired environment variables, this is ideal for credentials or application specific configurations.
5. Volume mapping is super easy, simply give the host path and container path as shown.

{% hint style="info" %}
**NOTICE:** We highly recommend keeping the Hosts stateless and using S3 for static assets. We will keep this field empty for this demo.
{% endhint %}

![](https://duplocloud.com/wp-content/uploads/2021/11/N1-service1.png)

Hit Submit! Please wait a moment for the service to initialize.

## Step 3: Create a load balancer <a href="#3-toc-title" id="3-toc-title"></a>

Almost there. Since the hello-nodejs image serves on port 3000 we need to create a load balancer (LB) configuration to map external port (LB) to internal port (container).

Select the Test-service and click the plus icon on the load balancer configuration table. Fill the menu as shown below and click submit.

![](https://duplocloud.com/wp-content/uploads/2021/11/N1-lb1.png)

Please wait for \~5 minutes as it can take a while for the Load Balancer to get provisioned.