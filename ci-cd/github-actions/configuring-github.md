---
description: This section discusses how you can configure Github to integrate with Duplo
---

# Configuring Github

## Prerequisites

### Deploy and test the applicatoin

To use GitHub CI/CD, you need to deploy the application with DuploCloud as a Service and test that it works as expected.

{% hint style="info" %}
GitHub CI/CD is recommended only for upgrades of container images and to run tests that can be written to run before or after.
{% endhint %}

## Obtain and configure an API token

In order to call a DuploCloud API from Github, you will need to obtain an API token.

{% content-ref url="../../administrator-tools/access-control/api-tokens.md" %}
[api-tokens.md](../../administrator-tools/access-control/api-tokens.md)
{% endcontent-ref %}

The basic steps are:

1. **(Recommended)** Create a "service account" user in DuploCloud that will own the API token.
2. Give the DuploCloud user access the desired tenant. See [adding tenants to a user](../../administrator-tools/access-control/tenant-access.md#adding-tenant-access-for-a-user).
3. Create an API token for that user. See [creating API Tokens](../../administrator-tools/access-control/api-tokens.md).
4. Add a Github Repository secret that contains the DuploCloud API token.

{% hint style="info" %}
**Note:** A 'service account' user in DuploCloud is just a user whose user name is not an email address, such as `github-bot` or `my-api-user`. These users are not able to log in.
{% endhint %}

## Adding Tenant access for users

{% content-ref url="../../administrator-tools/access-control/tenant-access.md" %}
[tenant-access.md](../../administrator-tools/access-control/tenant-access.md)
{% endcontent-ref %}

![](<../../.gitbook/assets/Screen Shot 2022-02-24 at 2.32.57 PM.png>)

{% hint style="warning" %}
The rest of this documentation will assume that you named the GitHub repository secret `DUPLO_TOKEN`.
{% endhint %}
