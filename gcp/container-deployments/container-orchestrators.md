---
description: Multiple container orchestration technologies for ease of consumption
---

# Container orchestration features

DuploCloud abstracts the complexity of container orchestration technologies, allowing you to focus on the deployment, updating, and debugging of your containerized application.&#x20;

Among the technologies supported are:

* **Google Kubernetes Engine (GKE)**: DuploCloud platform uses GKE, providing you with a user-friendly interface that conceals the complexities of Kubernetes. Using the UI you can add K8S configurations around Pods, Containers, Secrets, and so on.&#x20;
* **Kubernetes (AWS Elastic Kubernetes Service \[EKS])**: DuploCloud platform uses AWS EKS, providing you with a user-friendly interface that conceals the complexities of Kubernetes. Using the UI you can add K8S configurations around Pods, Containers, Secrets, and so on.&#x20;
* **AWS Elastic Container Service (ECS)**: AWS ECS is a Google Cloud Platform Partner. You can use ECS-enabled clusters with DuploCloud GCP.
* **Built-in (DuploCloud)**: DuploCloud platform's built-in container management has the same interface as the `docker run` command, except that it can be scaled to hundreds of containers across many hosts, providing capabilities such as associated load balancers, DNS, and more.

## Container orchestration feature matrix

Use the feature matrix below to compare the features of the orchestration technologies that DuploCloud supports.  DuploCloud helps you implement any option you choose through the Portal or the Terraform API.

{% hint style="info" %}
One dot indicates a low rating, two dots indicate a medium rating, and three dots indicate a high rating. For example, Kubernetes has a low ease-of-use rating, but a high rating for stateful application support.
{% endhint %}



<table><thead><tr><th align="center">Feature</th><th data-type="rating" data-max="3">Kubernetes</th><th data-type="rating" data-max="3">Built-In</th><th data-hidden data-type="rating" data-max="3">ACI</th></tr></thead><tbody><tr><td align="center">Ease of use</td><td>1</td><td>3</td><td>1</td></tr><tr><td align="center">Features and ecosystem Tools</td><td>3</td><td>1</td><td>1</td></tr><tr><td align="center">Suitability for stateful apps</td><td>3</td><td>1</td><td>1</td></tr><tr><td align="center">Stability and maintenance</td><td>2</td><td>3</td><td>2</td></tr><tr><td align="center">GCP cost</td><td>1</td><td>3</td><td>3</td></tr><tr><td align="center">Multi-cloud (w/o DuploCloud)</td><td>3</td><td>null</td><td>null</td></tr></tbody></table>

### **Feature definitions**

Use the definitions below to understand how each feature in the matrix above is rated in relation to each of the three listed technologies (Kubernetes, Built-In).&#x20;

* **Ease of Use**:&#x20;
  * Kubernetes is extensible and customizable, but not without a cost in ease of use. The DuploCloud platform reduces the complexities of Kubernetes, making it comparable with other container orchestration technologies in ease of adoption.
  * DuploCloud's Built-in orchestration mirrors `docker run`. You can SSH into a virtual machine (VM) and run `docker` commands to debug and diagnose. If you have an application with a few stateless microservices; or configurations that use environment variables or Google Cloud Extensions, Google Cloud Storage, or GCP Secret Manager, consider using DuploCloud's Built-in container orchestration.
* **Features and Ecosystem Tools**: Kubernetes is rich in many additional built-in features and ecosystem tools, most notably Secrets Management and ConfigMaps. Built-In and EKS Native rely on native services. While Kubernetes features have an equivalent in GCP, third parties tend to publish their software as Kubernetes packages (Helm Charts). Some examples are Influx DB, Time Series DB, Prefect, etc.
* **Suitability for Stateful apps**: Stateful applications should be avoided in GCP. Instead, cloud-managed storage solutions should be leveraged for the best availability and SLA compliance. In scenarios where this is undesirable due to cost, Kubernetes offers the best solution.  Kubernetes uses StatefulSets and Volumes to implicitly manage Google Cloud Storage volumes. With Built-in and EKS native, you must use a shared drive, which may not have feature parity with Kubernetes volume management.
* **Stability and Maintenance**: Although Kubernetes is highly stable, it is an open-source product. The native customizability and extensibility of Kubernetes can lead to points of failure when a mandatory cluster upgrade is needed, for example. This complexity often leads to support costs from third-party vendors. Maintenance can be costly with GKS, as versions are deprecated frequently and you are required to upgrade the control plane and data nodes. While DuploCloud automates this upgrade process, it still requires careful planning and execution.
* **GCP Cost**: While the GCP control plane cost is relatively low, it is not recommended to operate a GKE environment without business support at an additional premium. If you are a small business, you may be able to add the support tier when you need it and then turn it off to reduce costs. &#x20;
* **Multi-Cloud**: For many enterprises and independent software vendors this is a requirement, either immediately or in the future. While Kubernetes provides this benefit, DuploCloud's implementation is much easier to maintain and easier to implement.         &#x20;
