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

>[!NOTE]
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

If you want to authorize the PrivateLink for use with an internal staging environment, ???

### Microsoft Azure {#snowflake-azure}

For Microsoft Azure, you'll need to get the `privatelink-pls-id` to create the Azure private endpoint. Run the following commands in your Snowflake account to get your `privatelink-pls-id`:

`SELECT SYSTEM$GET_PRIVATELINK_CONFIG();`
`SELECT SYSTEM$ALLOWLIST_PRIVATELINK();`

When you have your `privatelink-pls-id`, you can send it to Adobe Customer Care so Adobe can create the Azure private endpoint for you.

Once Adobe creates the Azure private endpoint, you can get your private endpoint resource ID. Now that you have the private endpoint resource ID, contact Snowflake support to authorize your Snowflake account, while providing the resource ID.

With your 

## Amazon Redshift {#amazon-redshift}

