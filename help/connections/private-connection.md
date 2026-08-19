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

Once your AWS account has been authorized for use with Snowflake, you'll need to get values including the `privatelink-vpce-id`, `privatelink-account-url`, and `privatelink_ocsp-url` so you can get the VPC interface endpoint. 

You can get these values by running the following commands in your Snowflake account as the ACCOUNTADMIN:

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

Once you have run these commands, you can send the full SQL output to Adobe Customer Care so Adobe can create the VPC interface endpoint for you.

For more detailed information to create a PrivateLink connection with AWS, read the [AWS PrivateLink guide](https://docs.snowflake.com/en/user-guide/admin-security-privatelink).

If you want to authorize the PrivateLink for use with an internal staging environment, contact Adobe Customer Care to enable the environment.

For more detailed information to create a PrivateLink connection with AWS for internal staging environments, read the [AWS VPC interface endpoints for internal stages guide](https://docs.snowflake.com/en/user-guide/private-internal-stages-aws).

### Microsoft Azure {#snowflake-azure}

For Microsoft Azure, you'll need to get values including the `privatelink-pls-id`, `privatelink-account-url`, and `privatelink_ocsp-url` to create the Azure private endpoint. 

You can get these values by running the following commands in your Snowflake account:

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

Once you have run these commands, you can send the full SQL output to Adobe Customer Care so Adobe can create the Azure private endpoint for you.

Once Adobe creates the Azure private endpoint, you can get your private endpoint resource ID. Now that you have the private endpoint resource ID, contact Snowflake support to authorize your Snowflake account, while providing the resource ID.

For more detailed information to create a PrivateLink connection with Azure, read the [Azure PrivateLink guide](https://docs.snowflake.com/en/user-guide/privatelink-azure).

If you want to authorize PrivateLink for use with an internal staging environment, run the following command in Snowflake, while providing the internal stage resource ID which is provided by Adobe Customer Care:

`SELECT SYSTEM$AUTHORIZE_STAGE_PRIVATELINK_ACCESS('<internal-stage-private-endpoint-resource-id>');`

For more detailed information to create a PrivateLink connection with Azure for internal staging environments, read the [Azure private endpoints for internal stages guide](https://docs.snowflake.com/en/user-guide/private-internal-stages-azure).

## Amazon Redshift {#amazon-redshift}

Both Provisioned Clusters and Redshift Serverless support private connections with Federated Audience Composition. 

>[!IMPORTANT]
>
>Before starting, contact Adobe Customer Care to receive your Amazon Web Services (AWS) account ID and your Virtual Private Cloud (VPC) ID. You will need **both** of these values to gain cross-account endpoint access. For more detailed information on granting access to the VPC, read the [granting access to a VPC guide](https://docs.aws.amazon.com/redshift/latest/mgmt/managing-cluster-cross-vpc-console-grantor.html).

Once you have both the AWS and VPC IDs, go to the AWS Management Console to grant cross-account access for a managed VPC endpoint. 

For a provisioned cluster, note both the **Redshift Cluster identifier** and the **cluster owner AWS account ID** values. For a Redshift Serverless, note both the **workgroup name** and the **owner AWS account ID** values.

After getting these values, share those details with Adobe Customer Care so Adobe can create the managed VPC endpoint. Adobe then will share the following connection details with you: **Redshift endpoint URL**, **Redshift JDBC URL**, and **Redshift ODBC URL**.

## Databricks {#databricks}

>[!AVAILABILITY]
>
>In order to use private connectivity with Databricks, you **must** be on an Enterprise plan on Databricks. For more information on private connectivity with Databricks, read the [private link concepts guide](https://docs.databricks.com/aws/en/security/network/concepts/privatelink-concepts).

Using private connectivity with Databricks depends on which cloud provider your Databricks instance is on.

### Amazon Web Services {#databricks-aws}

Before configuring with Amazon Web Services, contact Adobe Customer Care so they can create a front-end (inbound) VPC interface endpoint that points to Databricks. This endpoint covers Federated Audience Composition's ODBC connectivity to your Databricks workspace.

Once you've gotten your VPC endpoint ID and AWS region from Adobe Customer Care, you'll need to register your VPC endpoint with the information provided by Adobe. 

After registering your VPC endpoint, you'll need to create a Private Access Settings (PAS) object. When you create the endpoint, set the **Private Access Level** to be at an **Endpoint** level and select the previously created VPC endpoint. For more information on creating private access settings, read the [configure inbound PrivateLink guide](https://docs.databricks.com/aws/en/security/network/front-end/front-end-private-connect#step-3-create-private-access-settings).

After configuring your private access settings, you can attach the VPC endpoint to your workspace. For more information on creating your workspace with PrivateLink, read the [configure inbound PrivateLink guide](https://docs.databricks.com/aws/en/security/network/front-end/front-end-private-connect#step-4-create-your-workspace-with-private-link-objects).

Now that all the settings have been configured, you can share your Databricks workspace URL with Adobe Customer Care. Once you've shared your Databricks workspace URL, Adobe can configure the DNS settings required to route requests to the workspace endpoint.

### Microsoft Azure {#databricks-azure}

A site-to-site VPN is used to connect securely from Adobe to the Databricks workspace on Azure. You'll need to set up an Azure VPN gateway to establish the VPN tunnel to securely transmit your data to Adobe.

Once you set up your Azure VPN Gateway and Databricks private endpoint, share the following details with your Adobe Customer Care representative: **Azure Virtual Network Gateway**, **Databricks Private Endpoint IP**, **Databricks Workspace URL**, and **Autonomous System Number (ASN)**.

With these details, Adobe can establish the VPN tunnels required for your connection. After establishing the VPN tunnels, Adobe provides the **VPN-Tunnel public and private IP addresses**, **pre-shared keys**, as well as an **autonomous system number**.

You can now configure your VPN tunnels in your Azure VNet Gateway. For more information, read the [connect AWS and Azure using a VPN gateway guide](https://learn.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-aws-bgp).

### Google Cloud Platform {#databricks-gcp}

A site-to-site VPN is used to connect securely from Adobe to the Databricks workspace on Google Cloud Platform. You'll need to set up a Google Cloud Platform High Availability VPN gateway and Cloud Router to establish the VPN tunnel to securely transmit your data to Adobe.

Once you set up your GCP HA VPN gateway and cloud router, share the following details with your Adobe Customer Care representative: **GCP HA VPN gateway**, **Databricks Workspace URL**, **Private Service Connect (PSC) IP**, and the **Autonomous System Number (ASN)**.

With these details, Adobe can establish the VPN tunnels required for your connection. After establishing the VPN tunnels, Adobe provides the **VPN-Tunnel public and private IP addresses**, **pre-shared keys**, as well as an **autonomous system number**.

You can now configure your VPN tunnels in your Google Cloud Platform account. For more information, read the [create HA VPN connections guide](https://docs.cloud.google.com/network-connectivity/docs/vpn/tutorials/create-ha-vpn-connections-google-cloud-aws).

## Azure Synapse Analytics {#azure-synapse}

To connect with Azure Synapse Analytics, you'll first need to create an Azure virtual network gateway and a Synapse private endpoint. The Azure virtual network gateway lets you send encrypted traffic between an Azure virtual network to Synapse, while the Synapse private endpoint lets you have a private connection to securely transmit your data.

Once you set up your Azure virtual network gateway and your Synapse private endpoint, share the following details with your Adobe Customer Care representative: **Azure Virtual Network Gateway**, **Synapse Private Endpoint IP**, **Synapse Workspace URL**, and **Autonomous Service Number (ASN)**. 

With these details, Adobe can establish the VPN tunnels required for your connection. After establishing the VPN tunnels, Adobe provides the **VPN-Tunnel pairings**, **pre-shared keys**, as well as an **autonomous system number**.

You can now configure your VPN tunnels in your Azure VNet Gateway. For more information, read the [connect AWS and Azure using a VPN gateway guide](https://learn.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-aws-bgp).

## Google Big Query {#gbq}

To connect with Google Big Query, you'll first need to create a Google Cloud Platform High Availability VPN gateway and a cloud router.

Once you set up your GCP HA VPN gateway and cloud router, share the following details with your Adobe Customer Care representative: **GCP HA VPN gateway**, **Private Service Connect (PSC) IP**, and the **Autonomous System Number (ASN)**.

With these details, Adobe can establish the VPN tunnels required for your connection. After establishing the VPN tunnels, Adobe provides the **VPN-Tunnel public and private IP addresses**, **pre-shared keys**, as well as an **autonomous system number**.

You can now configure your VPN tunnels in your Google Cloud Platform account. For more information, read the [create HA VPN connections guide](https://docs.cloud.google.com/network-connectivity/docs/vpn/tutorials/create-ha-vpn-connections-google-cloud-aws).
