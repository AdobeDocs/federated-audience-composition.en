---
audience: end-user
title: Get started with Federated Databases
description: Learn how to create and manage your Federated Databases
badge: label="Limited availability" type="Informative"
exl-id: b8c0589d-4150-40da-ac79-d53cced236e8
---
# Get started with Federated Databases {#federated-db}

>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_menu"
>title="Federated Databases"
>abstract="Existing connections to Federated Databases are listed in this screen. To create a new connection, click the **[!UICONTROL Add federated database]** button."

>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_properties"
>title="Federated Database properties"
>abstract="Enter the name of the new Federated Database, and select its type."

>[!CONTEXTUALHELP]
>id="dc_connection_federated_database_details"
>title="Federated Database details"
>abstract="Enter the settings to connect to the new Federated Database. Use the **[!UICONTROL Test connection]** button to validate your configuration."

Experience Platform Federated Audience Composition allows Customer to build and enrich audiences from the third-party data warehouses and import the audiences to Adobe Experience Platform.

Learn how to ceate, configure, test and save the connection to your external database in this page.

## Supported databases {#supported-db}

With Federated Audience Composition, you can connect to the following databases. Configuration for each database is detailed below.

* [Amazon Redshift](#amazon-redshift)
* [Azure Synapse](#azure-synapse-redshift)
* [Google Big Query](#google-big-query)
* [Snowflake](#snowflake)
* [Vertica Analytics](#vertica-analytics)

## Amazon Redshift {#amazon-redshift}

Use Federated Databases to process information stored in an external database. Follow the steps below to configure access to Amazon Redshift.

1. Under the **[!UICONTROL Federated data]** menu, select **[!UICONTROL Federated databases]**.

1. Click **[!UICONTROL Add federated database]**.

    ![](assets/federated_database_1.png)

1. Enter a **[!UICONTROL Name]** to your Federate database.

1. From the **[!UICONTROL Type]** drop-down, select Amazon Redshift.

    ![](assets/federated_database_6.png)

1. Configure the Amazon Redshift authentication settings:

    * **[!UICONTROL Server]**: Add the name of the DNS.

    * **[!UICONTROL Account]**: Add the username.

    * **[!UICONTROL Password]**: Add the account password.

    * **[!UICONTROL Database]**: Name of your database if not specified in DSN. It can be left empty if specified in the DSN

    * **[!UICONTROL Working schema]**: Name of the database schema to use for work tables. [Learn more](https://docs.aws.amazon.com/redshift/latest/dg/r_Schemas_and_tables.html)

        >[!NOTE]
        >
        >You can use any schema from the database, including schemas used for temporary data processing, as long as you have the required permission to connect to this schema.

1. Select the **[!UICONTROL Test the connection]** option to verify your configuration.

1. Click **[!UICONTROL Deploy functions]** button to create the functions.

1. Once your configuration is done, click **[!UICONTROL Add]** to create your Federate database.

## Azure Synapse Redshift {#azure-synapse-redshift}

Use Federated Databases to process information stored in an external database. Follow the steps below to configure access to Azure Synapse Redshift.

1. Under the **[!UICONTROL Federated data]** menu, select **[!UICONTROL Federated databases]**.

1. Click **[!UICONTROL Add federated database]**.

    ![](assets/federated_database_1.png)

1. Enter a **[!UICONTROL Name]** to your Federate database.

1. From the **[!UICONTROL Type]** drop-down, select Azure Synapse Redshift.

    ![](assets/federated_database_4.png)

1. Configure the Azure Synapse Redshift authentication settings:

    * **[!UICONTROL Server]**: Enter the URL of the Azure Synapse server.

    * **[!UICONTROL Account]**: Enter the Username.

    * **[!UICONTROL Password]**: Enter the account password.

    * **[!UICONTROL Database]** (optional): Enter the name of your database if not specified in the DSN.

    * **[!UICONTROL Options]**: The connector supports the options detailed in the table below.

1. Select the **[!UICONTROL Test the connection]** option to verify your configuration.

1. Click **[!UICONTROL Deploy functions]** button to create the functions.

1. Once your configuration is done, click **[!UICONTROL Add]** to create your Federate database.

| Option   |  Description |
|---|---|
| Authentication | Type of authentication supported by the connector. Current supported value: ActiveDirectoryMSI. For more information, refer to [SQL doc](https://learn.microsoft.com/en-us/sql/connect/odbc/using-azure-active-directory?view=sql-server-ver15#example-connection-strings) (Example connection strings n°8) |


## Google Big Query {#google-big-query}

Use Federated Databases to process information stored in an external database. Follow the steps below to configure access to Google Big Query.

1. Under the **[!UICONTROL Federated data]** menu, select **[!UICONTROL Federated databases]**.

1. Click **[!UICONTROL Add federated database]**.

    ![](assets/federated_database_1.png)

1. Enter a **[!UICONTROL Name]** to your Federate database.

1. From the **[!UICONTROL Type]** drop-down, select Google Big Query.

    ![](assets/federated_database_3.png)

1. Configure the Google Big Query authentication settings:

    * **[!UICONTROL Service account]**: Enter the email of your **[!UICONTROL Service account]**. For more information on this, refer to [Google Cloud documentation](https://cloud.google.com/iam/docs/creating-managing-service-accounts).

    * **[!UICONTROL Project]**: Enter the name of your **[!UICONTROL Project]**. For more information on this, refer to [Google Cloud documentation](https://cloud.google.com/resource-manager/docs/creating-managing-projects).

    * **[!UICONTROL Dataset]**: Enter the name of your **[!UICONTROL Dataset]**. For more information on this, refer to [Google Cloud documentation](https://cloud.google.com/bigquery/docs/datasets-intro).

    * **[!UICONTROL Key file Path]**: Upload your key file to the server. Only .json files are accepted.

    * **[!UICONTROL Options]**: The connector supports the options detailed in the table below.

1. Select the **[!UICONTROL Test the connection]** option to verify your configuration.

1. Click **[!UICONTROL Deploy functions]** button to create the functions.

1. Once your configuration is done, click **[!UICONTROL Add]** to create your Federate database.

| Option   |  Description |
|---|---|
|  ProxyType | Type of proxy used to connect to BigQuery through ODBC and SDK connectors. </br>HTTP (default), http_no_tunnel, socks4 and socks5 are currently supported. |
|  ProxyHost | Hostname or IP address where the proxy can be reached. |
| ProxyPort | Port number the proxy is running on, e.g. 8080 |
| ProxyUid | Username used for the authenticated proxy |
| ProxyPwd | ProxyUid password |
| bqpath | Note that this is applicable for bulk-load tool only (Cloud SDK). </br> To avoid using PATH variable or if the google-cloud-sdk directory has to be moved to another location, you can specify with this option the exact path to the cloud sdk bin directory on the server. |
| GCloudConfigName | Note that this is applicable starting release 7.3.4 release and  for bulk-load tool only (Cloud SDK).</br> The Google Cloud SDK uses configurations to load data into BigQuery tables. The configuration named `accfda` stores the parameters for loading the data. However, this option allows users to specify a different name for the configuration. |
| GCloudDefaultConfigName | Note that this is applicable starting release 7.3.4 release and for bulk-load tool only (Cloud SDK).</br> The active Google Cloud SDK configuration cannot be deleted without first transferring the active tag to a new configuration. This temporary configuration is necessary to recreate the main configuration for loading data. The default name for the temporary configuration is `default`, this can be changed if needed.|
| GCloudRecreateConfig | Note that this is applicable starting release 7.3.4 release and for bulk-load tool only (Cloud SDK).</br> When set to `false`, the bulk loading mechanism refrains from attempting to recreate, delete, or modify the Google Cloud SDK configurations. Instead, it proceeds with data loading using the existing configuration on the machine. This feature is valuable when other operations depend on Google Cloud SDK configurations. </br> If the user enables this engine option without a proper configuration, the bulk loading mechanism will issue a warning message: `No active configuration found. Please either create it manually or remove the GCloudRecreateConfig option`. To prevent further errors, it will then revert to using the default ODBC Array Insert bulk loading mechanism. |


## Snowflake {#snowflake}

Use Federated Databases to process information stored in an external database. Follow the steps below to configure access to Snowflake.

1. Under the **[!UICONTROL Federated data]** menu, select **[!UICONTROL Federated databases]**.

1. Click **[!UICONTROL Add federated database]**.

    ![](assets/federated_database_1.png)

1. Enter a **[!UICONTROL Name]** to your Federate database.

1. From the **[!UICONTROL Type]** drop-down, select Snowflake.

    ![](assets/federated_database_2.png)

1. Configure the Snowflake authentication settings:

    * **[!UICONTROL Server]**: Enter your Server name.

    * **[!UICONTROL User]**: Enter your Username.

    * **[!UICONTROL Password]**: Enter your account password.

    * **[!UICONTROL Database]** (optional): Enter the name of your database if not specified in the DSN.

    * **[!UICONTROL Working schema]** (optional): Enter the name of the database schema to use for work tables.

        >[!NOTE]
        >
        >You can use any schema from the database, including schemas used for temporary data processing, as long as you have the required permission to connect to this schema.

    * **[!UICONTROL Private key]**: Click the **[!UICONTROL Private key]** field to select your .pem files from your locale folder.

    * **[!UICONTROL Options]**: The connector supports the options detailed in the table below.

1. Select the **[!UICONTROL Test the connection]** option to verify your configuration.

1. Click **[!UICONTROL Deploy functions]** button to create the functions.

1. Once your configuration is done, click **[!UICONTROL Add]** to create your Federate database.

The connector supports the following options:

| Option   |  Description |
|---|---|
|  workschema | Database schema to use for work tables |
|  warehouse | Name of the default warehouse to use. It will override the user's default. |
|  TimeZoneName |  By default empty, which means that the system time zone of the Campaign Classic app server is used. The option can be used to force the TIMEZONE session parameter. <br>For more on this, refer to [this page](https://docs.snowflake.net/manuals/sql-reference/parameters.html#timezone). |
|  WeekStart |  WEEK_START session parameter. By default set to 0. <br>For more on this, refer to [this page](https://docs.snowflake.com/en/sql-reference/parameters.html#week-start). |
|  UseCachedResult | USE_CACHED_RESULTS session parameter. By default set to TRUE. This option can be used to disable Snowflake cached results. <br>For more on this, refer to [this page](https://docs.snowflake.net/manuals/user-guide/querying-persisted-results.html). |
|  bulkThreads | Number of threads to use for Snowflake bulk-loader, more threads mean a better performance for bigger bulk-loads. By default set to 1. The number can be adjusted, depending on the machine thread count. |
|  chunkSize | Determines the file size of the bulk-loader chunk. By default set to 128MB. Can be modified for a more optimal performance, when used with bulkThreads. More concurrently active threads mean better performance. <br>For more on this, refer to [Snowflake documentation](https://docs.snowflake.net/manuals/sql-reference/sql/put.html).|
| StageName | Name of the pre-provisioned internal stage. It will be used in bulk load instead of creating a new temporary stage.|


## Vertica Analytics {#vertica-analytics}

Use Federated Databases to process information stored in an external database. Follow the steps below to configure access to Vertica Analytics.

1. Under the **[!UICONTROL Federated data]** menu, select **[!UICONTROL Federated databases]**.

1. Click **[!UICONTROL Add federated database]**.

    ![](assets/federated_database_1.png)

1. Enter a **[!UICONTROL Name]** to your Federate database.

1. From the **[!UICONTROL Type]** drop-down, select Vertica Analytics.

    ![](assets/federated_database_5.png)

1. Configure the Vertica Analytics authentication settings:

    * **[!UICONTROL Server]**: Add the URL of the [!DNL Vertica Analytics] server.

    * **[!UICONTROL Account]**: Add the Username.

    * **[!UICONTROL Password]**: Add the account password.

    * **[!UICONTROL Database]** (optional): Enter the name of your database if not specified in the DSN.

    * **[!UICONTROL Working schema]** (optional): Enter the name of the database schema to use for work tables.

        >[!NOTE]
        >
        >You can use any schema from the database, including schemas used for temporary data processing, as long as you have the required permission to connect to this schema.

    * **[!UICONTROL Options]**: The connector supports the options detailed in the table below.

1. Select the **[!UICONTROL Test the connection]** option to verify your configuration.

1. Click **[!UICONTROL Deploy functions]** button to create the functions.

1. Once your configuration is done, click **[!UICONTROL Add]** to create your Federate database.

The connector supports the following options:

| Option   |  Description |
|---|---|
|  TimeZoneName |  By default empty, which means that the system time zone of the Campaign Classic app server is used. The option can be used to force the TIMEZONE session parameter. |
