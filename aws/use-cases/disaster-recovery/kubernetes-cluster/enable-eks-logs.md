---
description: Enable logging functionality for EKS
---

# Enable EKS logs

## Enabling EKS logging while creating an Infrastructure

Follow the steps in the section [Creating an Infrastructure](../../disaster-recovery.md). Before clicking **Create**, select the **EKS Logging list** box and select one or more **ControlPlane Log** types.

<figure><img src="../../../../.gitbook/assets/AWS_Infra_logs2.png" alt=""><figcaption><p><strong>EKS Logging</strong> field with several <strong>ControlPLane Log</strong> types selected</p></figcaption></figure>

## Enabling EKS logging for an existing Infrastructure

Enable EKS logging for an Infrastructure that you have created.

1. In the DuploCloud Portal, navigate to **Administrator** -> **Infrastructure**.
2. From the **Name** column, select the Infrastructure for which you want to enable EKS logging.
3. Click the **Settings** tab.
4. Click **Add**. The **Infra - Set Custom Data** pane displays.
5. From the **Setting Name** list box, select **EKS ControlPlane Logs**.
6. In the **Setting Value** field, enter: `api;audit;authenticator;controllerManager;scheduler`
7. Click **Set**. The **EKS ControlPlane Logs** setting is displayed in the **Settings** tab.

<figure><img src="../../../../.gitbook/assets/AWS_Infra_logs3.png" alt=""><figcaption><p><strong>Infra - Set Custom Data</strong> pane for setting <strong>EKS ControlPlane Logs</strong></p></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/AWS_logging_display.png" alt=""><figcaption><p><strong>Settings</strong> tab with <strong>EKS ControlPlane Logs</strong> <strong>Value</strong> set</p></figcaption></figure>

