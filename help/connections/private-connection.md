---
title: Connect to Federated Audience Composition using a private connection
description: Learn how to set up and connect to Federated Audience Composition using a private connection. This includes PrivateLink or a site-to-site VPN.
---

# Private connectivity to Federated Audience Composition

Federated Audience Composition supports private connections with multiple databases. Private connections let you connect to customer-hosted data warehouses without traversing the public internet.

## Supported databases {#supported-databases}

The following databases support private connectivity to Federated Audience Composition:

| Database | Cloud | Private connection type |
| -------- | ----- | ----------------------- |
| Snowflake | Amazon Web Services (AWS) | AWS PrivateLink (VPC interface endpoint) |
| Snowflake | Microsoft Azure | Azure PrivateLink (Private endpoint) |
| Amazon Redshift | Amazon Web Services (AWS) | AWS PrivateLink (Managed VPC endpoint) |
| Databricks | Amazon Web Services (AWS) | AWS PrivateLink (VPC interface endpoint) |
| Databricks | Microsoft Azure | Site-to-site VPN |
| Databricks | Google Cloud Platform (GCP) | Site-to-site VPN |
| Azure Synapse Analytics | Microsoft Azure | Site-to-site VPN |
| Google BigQuery | Google Cloud Platform (GCP) | Site-to-site VPN |

## Snowflake {#snowflake}

>[!AVAILABILITY]
>
>In order to use private connectivity with Snowflake, you **must** be at least on Business Critical tier or higher on Snowflake. For more information on private connectivity with Snowflake, read the [private connectivity guide in the Snowflake documentation](https://docs.snowflake.com/en/user-guide/private-connectivity-inbound).

Using private connectivity with Snowflake depends on which cloud provider your Snowflake instance is on.

### Amazon Web Services (AWS) {#snowflake-aws}

>[!IMPORTANT]
>
>Before continuing, make sure you get your AWS account ID from Adobe Customer Care. Once you get your AWS account ID, contact Snowflake support so Snowflake can authorize your AWS account to use PrivateLink.

Once your AWS account has been authorized for use with Snowflake, you'll need to get the `privatelink-vcpe-id` value so you can get the VPC interface endpoint. 

You can get the `privatelink-vcpe-id` value by running the following commands in your Snowflake account as the ACCOUNTADMIN:

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

Once you have the `privatelink-vcpe-id`, you can send it to Adobe Customer Care so Adobe can create the VPC interface endpoint for you.

For more detailed information to create a PrivateLink connection with AWS, read the [AWS PrivateLink guide](https://docs.snowflake.com/en/user-guide/admin-security-privatelink).

If you want to authorize the PrivateLink for use with an internal staging environment, contact Adobe Customer Care to enable the environment.

For more detailed information to create a PrivateLink connection with AWS for internal staging environments, read the [AWS VPC interface endpoints for internal stages guide](https://docs.snowflake.com/en/user-guide/private-internal-stages-aws).

### Microsoft Azure {#snowflake-azure}

For Microsoft Azure, you'll need to get the `privatelink-pls-id` to create the Azure private endpoint. Run the following commands in your Snowflake account to get your `privatelink-pls-id`:

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

When you have your `privatelink-pls-id`, you can send it to Adobe Customer Care so Adobe can create the Azure private endpoint for you.

Once Adobe creates the Azure private endpoint, you can get your private endpoint resource ID. Now that you have the private endpoint resource ID, contact Snowflake support to authorize your Snowflake account, while providing the resource ID.

For more detailed information to create a PrivateLink connection with Azure, read the [Azure PrivateLink guide](https://docs.snowflake.com/en/user-guide/privatelink-azure).

If you want to authorize PrivateLink for use with an internal staging environment, run the following command in Snowflake, while providing the internal stage resource ID:

`SELECT SYSTEM$AUTHORIZE_STAGE_PRIVATELINK_ACCESS('<internal-stage-private-endpoint-resource-id>');`

For more detailed information to create a PrivateLink connection with Azure for internal staging environments, read the [Azure private endpoints for internal stages guide](https://docs.snowflake.com/en/user-guide/private-internal-stages-azure).

## Amazon Redshift {#amazon-redshift}

Both Provisioned Clusters and Redshift Serverless support private connections with Federated Audience Composition. 

>[!IMPORTANT]
>
>Before starting, contact Adobe Customer Care to receive your Amazon Web Services (AWS) account ID and your Virtual Private Cloud (WPC) ID. You will need **both** of these values to gain cross-account endpoint access.

Once you have both the AWS and WPC IDs, go to the AWS Management Console and open the [Amazon Redshift console](https://console.aws.amazon.com/redshiftv2/). In the AWS Management Console, select **Clusters** if you're using Provisioned Clusters or **Serverless dashboard** if you're using Redshift Serverless.

Select the cluster you want to allow access to, and go to the **Properties** tab. Within the tab, select the account that contains the VPC ID you received from Adobe Customer Care. If you're using a Redshift Serverless workgroup, the **Granted accounts** section is under the **Data access** tab.

After selecting **Grant access**, you can enter the information within **Grantee information**. This includes the AWS account ID that you received from Adobe Customer Care.

Now that you've granted access, you'll need to note the following details in the cluster about the managed VPC endpoint. For a provisioned cluster, note the **Redshift Cluster Identifier** and the **Cluster Owner AWS Account ID**. For Redshift Serverless, note the **Workgroup Name** and the **Owner AWS Account ID**. 

With the relevant information noted, share those details with Adobe Customer Care so Adobe can create the managed VPC endpoint. Adobe then will share the following connection details with you: **Redshift endpoint URL**, **Redshift JDBC URL**, and **Redshift ODBC URL**.

## Databricks {#databricks}

>[!AVAILABILITY]
>
>In order to use private connectivity with Databricks, you **must** be on an Enterprise plan on Databricks. For more information on private connectivity with Databricks, read the [private link concepts guide](https://docs.databricks.com/aws/en/security/network/concepts/privatelink-concepts).

Using private connectivity with Databricks depends on which cloud provider your Databricks instance is on.

### Amazon Web Services {#databricks-aws}

Before configuring with Amazon Web Services, contact Adobe Customer Care so they can create a front-end (inbound) VPC interface endpoint that points to Databricks. This endpoint covers Federated Audience Composition's ODBC connectivity to your Databricks workspace.

Once you've gotten your VPC endpoint ID and AWS region from Adobe Customer Care, open your Databricks account so you can register the endpoint. In your Databricks account, go to **Cloud resources**, followed by **Network**, and **VPC endpoint registrations**. 

The **Register new VPC endpoint** page is displayed. Choose the region that matches your AWS VPC endpoint and paste the VPC endpoint ID you received from Adobe Customer Care. 

Once you've added all the required information, select **Register new VPC endpoint**. For more information about configuring your VPC connection for Databricks, read the [configure inbound PrivateLink guide](https://docs.databricks.com/aws/en/security/network/front-end/front-end-private-connect#step-2-register-vpc-endpoints).

Now that you've registered your VPC endpoint, you'll need to create a Private Access Settings (PAS) object. In your Databricks account, go to **Security** followed by **Private access settings** and **Add private access settings**. 

The **Add private access setting** page is displayed. When you add the necessary information, make sure you set the **Private Access Level** to be at an **Endpoint** level. 

Once you've chosen endpoint level, select the previously created VPC endpoint and complete the private access setting setup. For more information on creating private access settings, read the [configure inbound PrivateLink guide](https://docs.databricks.com/aws/en/security/network/front-end/front-end-private-connect#step-3-create-private-access-settings).

After configuring your private access settings, you can attach the VPC endpoint to your workspace. In your Databricks account, go to **Advanced configurations** followed by **Private Link** and select the previously created private access settings object. For more information on creating your workspace with PrivateLink, read the [configure inbound PrivateLink guide](https://docs.databricks.com/aws/en/security/network/front-end/front-end-private-connect#step-4-create-your-workspace-with-private-link-objects).

Now that all the settings have been configured, you can share your Databricks workspace URL with Adobe Customer Care. Once you've shared your Databricks workspace URL, Adobe can configure the DNS settings required to route requests to the workspace endpoint.

### Microsoft Azure {#databricks-azure}

Since Databricks does not natively support Microsoft Azure, you'll first need to create an Azure VPN Gateway. The Azure VPN Gateway service lets you send encrypted traffic between an Azure virtual network to Databricks.

To set up an Azure VPN gateway, 