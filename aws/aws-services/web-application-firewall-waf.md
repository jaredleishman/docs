---
description: Creating and Using a WAF in DuploCloud AWS
---

# Web App Firewall (WAF)

The creation of a Web Application Firewall (WAF) is a one-time process. Create a WAF in the Azure Console, fetch the ID/ARN, and update the Plan in DuploCloud. Once updated, the WAF can be attached to the Load Balancer.&#x20;

## Creating a Web Application Firewall (WAF)

When you create a WAF in DuploCloud, an entry is added to the [AWS Web ACL](https://docs.aws.amazon.com/waf/latest/developerguide/web-acl.html). You use this entry [in a later step](web-application-firewall-waf.md#attaching-the-waf-to-a-load-balancer) to attach an ALB Load Balancer to your WAF.

1.  In the DuploCloud Portal, navigate to **Administrator** -> **Plans**. The **Plans** page displays.

    ![Plans page with WAF tab](https://duplocloud.com/wp-content/uploads/2021/11/plan-waf.png)
2. From the **Name** column, select the Plan you want to update.
3.  Click **Add**. The **Add WAF** pane displays.

    <figure><img src="../../.gitbook/assets/Azure_WAF (1).png" alt=""><figcaption><p><strong>Add WAF</strong> pane</p></figcaption></figure>
4. In the **Name** field, type the name of your WAF.
5. In the **WAF ARN** field, enter the Amazon Resource Name (ARN).
6. Click **Create**.

## Attaching the WAF to a Load Balancer

{% hint style="warning" %}
Only ALB Load Balancers can be attached to a WAF.
{% endhint %}

1. If you don't yet have an Application Load Balancer (ALB), [create one](load-balancers.md#adding-a-load-balancer).
2. In the DuploCloud Portal, navigate to **DevOps** -> **Containers** -> **EKS/Native**.
3. From the **Name** column, select the Service running the ALB Load Balancer.
4. Click the **Load Balancers** tab.
5.  Use the **LB Listeners** card to [add a Load Balancer Listener](load-balancers.md#adding-a-load-balancer-listener) for your ALB Load Balancer. If you have a Load Balancer Listener for ALB, click the Edit Icon ( <img src="../../.gitbook/assets/image (3).png" alt="" data-size="line">) to display or **Update** details, as in the graphic below.

    ![Edit Load Balancer Listener pane displaying details of an ALB Load Balancer for a WAF](../../.gitbook/assets/AWS\_ALB\_LBL\_HTTP.png)
6.  In the **Other Settings** card, click **Edit**. The **Other Load Balancer Settings** pane displays.

    <figure><img src="../../.gitbook/assets/AWS_LB_WAF_Attach.png" alt=""><figcaption><p><strong>Other Load Balancer Settings</strong> for attaching a WAF (via the <strong>Web ACL</strong> field) to an ALB Load Balancer</p></figcaption></figure>
7. From the **Web ACL** list box, select a [WAF that you have added to DuploCloud](web-application-firewall-waf.md#creating-a-web-application-firewall-waf).&#x20;
8. Complete the other required fields in the **Other Load Balancer Settings** pane.
9. Click **Update**.

## Analyzing inbound traffic with the WAF dashboard <a href="#1-toc-title" id="1-toc-title"></a>

DuploCloud also provides a WAF Dashboard through which you can analyze the traffic that is coming in and the requests that are blocked. The Dashboard can be accessed from the left navigation panel: **Security > WAF**.

![WAF Dashboard](<../../.gitbook/assets/waf (1).png>)
