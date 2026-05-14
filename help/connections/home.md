---
audience: end-user
title: Create and manage connections with Federated databases
description: Learn how to create and manage connections with Federated databases
exl-id: ab65cd8a-dfa0-4f09-8e9b-5730564050a1
TQID: https://experienceleague.adobe.com/6-pzawt2ndn2MKLyYLXPMy-ec1SIOsQI5frTt9IqOX0
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
    internal-label: Integrations
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Create connections {#connections-fdb}

>[!AVAILABILITY]
>
>To access connections, you'll need one of the following permissions:
>
>-**Manage Federated Database**
>-**View Federated Database**
>
>For more information on the required permissions, please read the [access control guide](/help/governance-privacy-security/access-control.md).

Experience Platform Federated Audience Composition lets you build and enrich audiences from the third-party data warehouses and import the audiences to Adobe Experience Platform.

## Supported databases {#supported-databases}

To work with your federated database and Adobe Experience Platform, you must first establish a connection between the two sources. With Federated Audience Composition, you can connect to the following databases.

- Amazon Redshift
- Azure Synapse Analytics
- Databricks
- Google BigQuery
- Microsoft Fabric
- Oracle
- Snowflake
- Teradata
- Vertica Analytics

## Create connection {#create}

To create a connection, select **[!UICONTROL Federated databases]** within the Federated data section.

![The Federated Databases button is highlighted within the left navigation.](assets/home/select-federated.png){zoomable="yes" width="70%" align="center"}

The Federated databases section appears. Select **[!UICONTROL Add federated database]** to create a connection.

![The Add federated database button is highlighted within the Federated database display page.](assets/home/add-federated.png){zoomable="yes" width="70%" align="center"}

>[!NOTE]
>
>In order to request secure connectivity using private link or VPN, you **must** have licensed either Privacy and Security Shield or Healthcare Shield.

The connection properties popover appears. You can name your connection as well as select what type of database you want to create.

![The federated database types are displayed.](assets/home/select-type.png){zoomable="yes" width="70%" align="center"}

After selecting a type, the **[!UICONTROL Details]** section appears. This section differs based on the database type previously chosen.

>[!BEGINTABS]

>[!TAB Amazon Redshift]

>[!AVAILABILITY]
>
>Only Amazon Redshift AWS, Amazon Redshift Spectrum, and Amazon Redshift Serverless are supported.
>
>Additionally, secure access to your external Amazon Redshift data warehouse through private link is supported.

After selecting Amazon Redshift, you can add the following details: 

| Field | Description |
| ----- | ----------- |
| Server | The name of the data source. |
| Account | The account's username. |
| Password | The account's password. |
| Database | The name of the database. If this is specified in the server name, this field can be left blank. |
| Working schema | The name of the database's schema to use for work tables. More information about this feature can be found in the [Amazon Schemas documentation](https://docs.aws.amazon.com/redshift/latest/dg/r_Schemas_and_tables.html){target="_blank"}.<br/><br/>**Note:** You can use any schema from the database, including schemas used for temporary data processing, as long as you have the required permissions to connect to this schema. However, you **must** use distinct working schemas when connecting multiple sandboxes with the same database. |

>[!TAB Azure Synapse Analytics]

>[!NOTE]
>
>If you want to create a secure connection using Azure Synapse Analytics, please contact your Adobe Customer Care representative.

After selecting Azure Synapse Analytics, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Server | The URL of the Azure Synapse server. |
| Account | The application ID (**Client ID**) of the Azure app registration. |
| Password | The **Client secret** value of the Azure application. |
| Database | The name of the database. If this is specified in the server name, this field can be left blank. |
| Options | Additional options for the connection. For Azure Synapse Analytics, you can specify the type of authentication supported by the connector. Currently, Federated Audience Composition supports `ActiveDirectoryMSI`. For more information about connection strings, please read the [example connection strings section within Microsoft's documentation](https://learn.microsoft.com/en-us/sql/connect/odbc/using-azure-active-directory?view=sql-server-ver15#example-connection-strings){target="_blank"} . |

Alternatively, you can securely configure your Azure Synapse Analytics connection by using Service Principal authentication. You should use Service Principal authentication for production-grade integrations as well as automation scenarios.

+++ Prerequisites

Before setting up your Service Principal authentication, please note the following prerequisites:

- An Azure subscription with access to Microsoft Entra ID
- An Azure Synapse workspace and database
- Permission to create App Registration
- Permission to manage Azure Synapse database roles
- Permission to update Federated Database configurations

+++

Within the Azure Portal, you'll first need to create a new app registration. Select **Register** after giving the application a unique name. The **Overview** page appears. Make sure you note the **Application (Client) ID** and the **Directory (Tenant) ID** values.

![The Application (Client) ID within the overview page is highlighted.](/help/connections/assets/home/azure-client-id.png)

Within the newly registered application, select **Certificates & secrets**. From here, select **New client secret** within the **Client secrets** section to create a new client secret. After providing a description and expiry, select **Add** to generate the client secret.

>[!IMPORTANT]
>
>After generating your client secret, copy and securely store your **Client Secret Value**. This value will **not** be visible again.

Now that you've generated your client secret, you need to make sure you've granted the **Service principal** identity to the resource.

For more information on assigning identity to resources, read the [Managed identities for Azure Synapse Analytics guide](https://learn.microsoft.com/en-us/azure/synapse-analytics/synapse-service-identity).

Since you've finished all your Azure-side configurations, you can now set up your Federated-Audience-Composition-side configurations.

Within your Azure Synapse connection, set the following configuration details:

| Field | Description |
| ----- | ----------- |
| Server | The URL of the Azure Synapse server. |
| Account | The application ID (**Client ID**) of the Azure app registration. |
| Password | The **Client secret** value of the Azure application. |
| Database | The name of the database. If this is specified in the server name, this field can be left blank. |
| Options | Additional options for the connection. In order to use Service Principal authentication, you'll need to set `Authentication="ActiveDirectoryServicePrincipal"`. |

>[!TAB Databricks]

>[!NOTE]
>
>Secure access to your external Databricks data warehouse through private link is supported. This includes secure connections to Databricks databases hosted on Amazon Web Services (AWS) via private link and Databricks databases hosted on Microsoft Azure via VPN. Please contact your Adobe representative for assistance in setting up secure access.

After selecting Databricks, you can choose with authentication method you want to use when connecting with Federated Audience Composition.

If you select **Account/Password Authentication**, you can add the following login details:

| Field | Description |
| ----- | ----------- |
| Server | The name of the Databricks server. |
| Password | The access token for the Databricks server. For more information on this value, please read the [Databricks documentation on personal access tokens](https://docs.databricks.com/aws/en/dev-tools/auth/pat){target="_blank"}.  |

If you select **Service Principal Authentication**, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Server | The name of the Databricks server. |
| Client ID | The client ID from your Databricks server. This field acts like a username for your project. |
| Client Secret | The client secret from your Databricks server. This field acts like a password for your project. |

If you select **OAuth 2.0**, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Server | The name of the Databricks server. |
| Client ID | The client ID from your Databricks server. This field is used to identify the application during OAuth 2.0 authentication and acts like a username for your project. |
| Client Secret | The client secret from your Databricks server. This confidential credential is issued with the client ID and acts like a password for your project. |
| Access scope | Prepopulated information that lists the scopes that your OAuth token is authorized for within your Databricks server. |

After inputting your login details, you can add the following information:

| Field | Description |
| ----- | ----------- |
| HTTP path | The path to your Cluster or Warehouse. For more information on the path, please read the [Databricks documentation on connection details](https://docs.databricks.com/aws/en/integrations/compute-details){target="_blank"}. |
| Catalog | The name of the Databricks Catalog. For more information on catalogs in Databricks, please read the [Databricks documentation on catalogs](https://docs.databricks.com/aws/en/catalogs/){target="_blank"} |
| Working schema | The name of the database schema to use for the work tables. <br/><br/>**Note:** You can use **any** schema from the database, including schemas used for temporary data processing, as long as you have the required permissions to connect to this schema. However, you **must** use distinct working schemas when connecting multiple sandboxes with the same database. |
| Options | Additional options for the connection. The available options are listed in the following table. |

For Databricks, you can set the following additional options: 

| Options | Description |
| ------- | ----------- |
| TimeZoneName | The name of the time zone to use. This value represents the `TIMEZONE` session parameter. For more information on time zones, please read the [Databricks documentation on timezones](https://docs.databricks.com/aws/en/sql/language-manual/parameters/timezone#:~:text=The%20system%20default%20is%20UTC%20.){target="_blank"}. |

>[!TAB Google BigQuery]

>[!NOTE]
>
>Secure access to your external Google BigQuery data warehouse through VPN is supported.

After selecting Google BigQuery, you can choose which authentication method you want to use when connecting with Federated Audience Composition.

If you select **[!UICONTROL Account/Password Authentication]**, you can add the following login information:

| Field | Description |
| ----- | ----------- |
| Service account | The email address of your service account. For more information, please read the [Google Cloud service account documentation](https://cloud.google.com/iam/docs/service-accounts-create){target="_blank"}. |

If you select **[!UICONTROL OAuth 2.0]**, you can add the following login information:

>[!NOTE]
>
>Before connecting to Google BigQuery using OAuth 2.0, you'll need to configure your redirect URL in your Google Cloud project. Add the redirect URL `https://fac-oauth.adobe.io/oauth` to your Google Cloud project under your OAuth 2.0 Client ID configuration.

| Field | Description |
| ----- | ----------- |
| Client ID | The client ID from your Google BigQuery project. This field acts like a username for your project. |
| Client Secret | The client secret from your Google BigQuery project. This field acts like a password for your project. |
| Access scope | Prepopulated information that lists the scopes your OAuth token is authorized for within your Google Cloud resources. |

Select **[!UICONTROL Sign in]** to finish your authentication.

If you select **[!UICONTROL WIF]**, you do **not** need to provide any login information. However, you **must** add the client library configuration as the **[!UICONTROL Key file path]**. For more information on the client library configuration, read the [Google BigQuery (Workload Identity Federation) configuration section](#wif-configuration).

After inputting your login details, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Project | The ID of your project. For more information, please read the [Google Cloud project documentation](https://cloud.google.com/resource-manager/docs/creating-managing-projects){target="_blank"}. |
| Dataset | The name of the dataset. For more information, please read the [Google Cloud dataset documentation](https://cloud.google.com/bigquery/docs/datasets-intro){target="_blank"}. |
| Key file path | The key file to the server. Only `json` files are supported. |
| Options | Additional options for the connection. The available options are listed in the following table. |

For Google BigQuery, you can set the following additional options:

| Options | Description |
| ------- | ----------- |
| ProxyType | The type of proxy used to connect to BigQuery. Supported values include `HTTP`, `http_no_tunnel`, `socks4`, and `socks5`. |
| ProxyHost | The hostname or IP address where the proxy can be reached. |
| ProxyUid | The port number that the proxy is running on. |
| ProxyPwd | The password for the proxy. |
| bgpath | **Note:** This is only applicable for the **bulk-load tool** (Cloud SDK). <br/><br/> The path to the Cloud SDK bin directory on the server. You only need to set this if you've moved the `google-cloud-sdk` directory to another location or if you want to avoid using the PATH variable. |
| GCloudConfigName | **Note:** This is only applicable for the **bulk-load tool** (Cloud SDK) above version 7.3.4. <br/><br/> The name of the configuration that stores the parameters for loading the data. By default, this value is `accfda`. |
| GCloudDefaultConfigName | **Note:** This is only applicable for the **bulk-load tool** (Cloud SDK) above version 7.3.4. <br/><br/> The name of the temporary configuration to recreate the main configuration for loading data. By default, this value is `default`. |
| GCloudRecreateConfig | **Note:** This is only applicable for the **bulk-load tool** (Cloud SDK) above version 7.3.4. <br/><br/> A boolean value that lets you decide if the bulk loading mechanism should automatically recreate, delete, or modify the Google Cloud SDK configurations. If this value is set to `false`, the bulk loading mechanism loads data using an existing configuration on the machine. If this value is set to `true`, ensure your configuration is properly set up - otherwise, the `No active configuration found. Please either create it manually or remove the GCloudRecreateConfig option` error will appear, and the loading mechanism will revert to the default loading mechanism. |

>[!TAB Microsoft Fabric]

After selecting Microsoft Fabric, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Server | The URL for the Microsoft Fabric server. |
| Application ID | The application ID for Microsoft Fabric. For more information about the application ID, please read the [Microsoft Fabric documentation on application setup](https://learn.microsoft.com/en-us/fabric/workload-development-kit/create-entra-id-app){target="_blank"}. |
| Client secret | The client secret for the application. For more information about the client secret, please read the [Microsoft Fabric documentation on application setup](https://learn.microsoft.com/en-us/fabric/workload-development-kit/create-entra-id-app#step-8-generate-a-secret-for-your-application){target="_blank"}. |
| Options | Additional options for the connection. The available options are listed in the following table. |

For Microsoft Fabric, you can set the following additional options:

| Option | Description |
| ------ | ----------- |
| Authentication | The type of authentication used by the connector. Supported values include: `ActiveDirectoryMSI`. For more information, please read the [Microsoft documentation on warehouse connectivity](https://learn.microsoft.com/en-us/fabric/data-warehouse/connectivity){target="_blank"}. |

>[!TAB Oracle]

>[!NOTE]
>
>Federated Audience Composition supports federated connection setup with Oracle databases on version 11g or higher and hosted on AWS, Azure, Exadata, or a private cloud (as long as it's accessible by an outside network). If you have any further queries related to Oracle database setup or need to create a secure connection to Oracle, please contact your Adobe Customer Care representative.

After selecting Oracle, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Server | The URL for the Oracle server. |
| Account | The username of the account. |
| Password | The password of the account. |

>[!TAB Snowflake]

>[!NOTE]
>
>Secure access to your external Snowflake data warehouse through private link is supported. Note that your Snowflake account must be hosted on Amazon Web Services (AWS) or Azure and located in the same region as your Federated Audience Composition environment. Please contact your Adobe representative for assistance in setting up secure access to your Snowflake account.

After selecting Snowflake, you can choose which authentication method you want to use when connecting with Federated Audience Composition.

If you select **[!UICONTROL Account/Password Authentication]**, you can add the following login information:

| Field | Description |
| ----- | ----------- |
| Server | The name of the server. |
| User | The username for the account. |
| Password | The password for the account. |

Alternatively, you can also provide a private key instead of providing a password. If you add a private key, you need to give the following information:

| Field | Description |
| ----- | ----------- |
| Server | The name of the server. |
| User | The username for the account. |
| Private key | The private key for the account. Only `.pem` files are supported. |
| Password | (Optional) The password for the account. |

If you select **[!UICONTROL OAuth 2.0]**, you can add the following login information:

>[!NOTE]
>
>Before connecting to Snowflake using OAuth 2.0, you'll need to configure your redirect URL in your Snowflake OAuth integration object. Add the redirect URL `https://fac-oauth.adobe.io/oauth` to your Snowflake OAuth integration configuration.

| Field | Description |
| ----- | ----------- |
| Server | The name of the server. |
| Client ID | The client ID from your Snowflake project. This field acts like a username for your project. |
| Client Secret | The client secret from your Snowflake project. This field acts like a password for your project. |

Select **[!UICONTROL Sign in]** to finish your authentication.

After inputting your login details, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Database | The name of the database. If this is specified in the server name, this field can be left blank. |
| Working schema | The name of the database schema to use for the work tables. <br/><br/>**Note:** You can use **any** schema from the database, including schemas used for temporary data processing, as long as you have the required permissions to connect to this schema. However, you **must** use distinct working schemas when connecting multiple sandboxes with the same database. |
| Private key | The private key for your database connection. You can upload a `.pem` file from your local system. |
| Options | Additional options for the connection. The available options are listed in the following table. |

For Snowflake, you can set the following additional options:

| Options | Description |
| ------- | ----------- |
| workschema | The name of the database schema to use for work tables. |
| TimeZoneName | The name of the time zone to use. This value represents the `TIMEZONE` session parameter. By default, the system time zone will be used. For more information on time zones, please read the [Snowflake documentation on timezones](https://docs.snowflake.com/en/sql-reference/parameters#timezone){target="_blank"}. |
| WeekStart | The day that you want the week to start. This value represents the `WEEK_START` session parameter. For more information on week start, please read the [Snowflake documentation on the week start parameter](https://docs.snowflake.com/en/sql-reference/parameters#week-start){target="_blank"}|
| UseCachedResult | A boolean that determines if Snowflake's cached results will be used. This value represents the `USE_CACHED_RESULTS` session parameter. By default, this value is set to true. For more information on this parameter, please read the [Snowflake documentation on persisting results](https://docs.snowflake.com/en/user-guide/querying-persisted-results){target="_blank"}. |
| bulkThreads | The number of threads to use for Snowflake's bulk loader. The more threads added, the better the performance will be for bigger bulk loads. By default, this value is set to 1. |
| chunkSize | The file size of the each bulk loader's chunk. When used concurrently with more threads, you can improve the performance of your bulk loads. By default, this value is set to 128 MB. For more information about chunk sizes, please read the [Snowflake documentation on preparing data files](https://docs.snowflake.com/en/user-guide/data-load-considerations-prepare){target="_blank"}. |
| StageName | The name of a pre-provisioned internal staging enviornment. This can be used in bulk loads instead of creating a new temporary stage. |

>[!TAB Teradata]

>[!NOTE]
>
>To connect with Teradata, you **must** complete various prerequisites, including installing database drivers. Please contact your Adobe Customer Care representative for more information.

After selecting Teradata, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Server | The URL of the Teradata server. |
| Account | The username the database uses for the Open Database Connectivity (ODBC) session. |
| Password | The password that you use to connect to the ODBC session. |
| Database | The name of the database. |
| Options | Additional options for the connection. For Teradata, both the listed options are **mandatory** to add. The available options are listed in the following table. |

For Teradata, you can set the following additional options:

| Options | Description |
| ------- | ----------- |
| `workTableSchema` | The name of the schema for the work tables. |
| `ODBCLib` | The location of the system's ODBC library, which you can use if you're mixing Teradata with another ODBC. |

>[!TAB Vertica Analytics]

After selecting Vertica Analytics, you can add the following details:

| Field | Description |
| ----- | ----------- |
| Server | The URL of the Vertica Analytics server. |
| Account | The username of the account. |
| Password | The password of the account. |
| Database | The name of the database. If this is specified in the server name, this field can be left blank. |
| Working schema | The name of the database schema to use for the work tables. <br/><br/>**Note:** You can use **any** schema from the database, including schemas used for temporary data processing, as long as you have the required permissions to connect to this schema. However, you **must** use distinct working schemas when connecting multiple sandboxes with the same database. |
| Options | Additional options for the connection. The available options are listed in the following table. |

For Vertica Analytics, you can set the following additional options:

| Options | Description |
| ------- | ----------- |
| TimeZoneName | The name of the time zone to use. This value represents the `TIMEZONE` session parameter. For more information on timezones, please read the [Vertica Analytics documentation on timezones](https://docs.vertica.com/24.1.x/en/admin/configuring-db/config-procedure/using-time-zones-with/){target="_blank"} |

>[!ENDTABS]

After adding the connection's details, please note the following additional settings:

>[!NOTE]
>
>To use Federated Audience Composition for a given database, you must allow list **all** of the IP addresses associated with that database.

| Settings | Details |
| -------- | ------- |
| Enable connection | A boolean toggle that determines whether the connection will automatically be enabled. |
| Server IPs | A popover that displays what IP addresses need to be allowlisted to connect to the database. |
| Test connection | Lets you verify your configuration details. |

You can now select **[!UICONTROL Deploy functions]**, followed by **[!UICONTROL Add]** to finalize the connection between the federated database and Experience Platform.

## Appendix {#appendix}

The following appendix describes how to set up the connections on the external account's side.

### Google BigQuery (Workload Identity Federation) configuration {#wif-configuration}

Before you configure your Google Cloud Platform setup, Adobe will provide you the following details:

- AWS Account ID
- AWS IAM role name

In Google Cloud Console, create a **Workload Identity Pool** in the **IAM & Admin section**. This lets you organize and manage external identities.

IMAGE

Select **Add provider** to create an identity provider. This configures a one-way trust between the identity provider in Google Cloud and the Worker Identity Pool by providing the relevant metadata about the provider.

IMAGE

When you create a provider, you'll need to provide the following information:

| Field | Description |
| ----- | ----------- |
| Name | The name of the Workload Identity Pool provider. |
| ID | The ID for the provider is automatically generated. |
| AWS account ID | The previously provided AWS Account ID. |
| Enabled provider | A boolean that determines of the provider is enabled or disabled. | 
| Attribute mapping | The mappings to match with the roles. This information is already present. |

After creating the provider, you need to create an IAM policy to let the Workload Identity Pool identities impersonate the Service Account. Select **Grant access** to open the Grant access to service account dialog.

In the dialog, select **Grant access using service account impersonation**. Within the **Select principals** section, you'll need to create your attribute mappings. 

Select **aws_role** and add `arn:aws:sts::AWSAccountID:assumed-role/AWSRoleName` as the value, substituting `AWSAccountID` and `AWSRoleName` with the previously provided values.

IMAGE

After granting access to the service account, download the client library configuration.

IMAGE

After downloading the client library configuration, you can now set up a WIF connection with Federated Audience Configuration.
