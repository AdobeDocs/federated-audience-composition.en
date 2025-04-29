---
title: Permissions for accessing an external database
description: Learn about rights specific to each database engine
---
# FDA Rights matrix {#fda-rights}

The table below outlines the required database privileges for each system, enabling users to perform operations on external databases through FDA.

| &nbsp;| Snowflake  | Redshift | Google BigQuery | Databricks |
|:-:|:-:|:-:|:-:|:-:|
| **Connecting to remote database**  | USAGE ON WAREHOUSE, USAGE ON DATABASE and USAGE ON SCHEMA privileges  | Creating a user linked to the AWS account  | Create a service account and grant principal access to project  | USE CATALOG privilege on Catalog and CAN_USE privilege on SQL Warehouse |
| **Creating tables** |  CREATE TABLE ON SCHEMA privilege | CREATE privilege  | Role assigned to service account has to contain: bigquery.jobs.create and bigquery.tables.create permissions |  USE SCHEMA privilege and CREATE TABLE privilege |
| **Creating indexes** | N/A |  CREATE privilege | BigQuery only support search indexes. Role assigned to service account has to contain: bigquery.jobs.create, bigquery.tables.getData and bigquery.tables.createIndex permissions  | N/A |
|  **Creating functions** |  CREATE FUNCTION ON SCHEMA privilege |  USAGE ON LANGUAGE plpythonu privilege to be able to call external python scripts |  Role assigned to service account has to contain: bigquery.jobs.create and bigquery.routines.create permissions |  CREATE FUNCTION privilege |
| **Creating procedures** | N/A  | USAGE ON LANGUAGE plpythonu privilege to be able to call external python scripts | Role assigned to service account has to contain: bigquery.jobs.create and bigquery.routines.create permissions | N/A | 
| **Removing objects (tables, indexes, functions, procedures)**  |  Owning the object | Owning the object or being a superuser  |  Role assigned to service account has to contain: bigquery.jobs.create, bigquery.routines.delete, bigquery.tables.delete and bigquery.tables.deleteIndex permissions  | 
| **Monitoring executions**  | MONITOR privilege on the required object  |  No privilege required to use EXPLAIN command | monitoring.viewer role | CAN_VIEW privilege |
|  **Writing data** |  INSERT and/or UPDATE privileges (depending on write operation) | INSERT and UPDATE privileges  | Role assigned to service account has to contain: bigquery.jobs.create and bigquery.tables.updateData |  MODIFY privilege | 
| **Loading data into tables** |  CREATE STAGE ON SCHEMA, SELECT and INSERT on the target table privileges |  SELECT and INSERT privileges | Role assigned to service account has to contain: bigquery.jobs.create, bigquery.tables.getData and bigquery.tables.updateData | SELECT and MODIFY privileges | 
| **Accessing to client data**  |  SELECT on (FUTURE) TABLE(S) or VIEW(S) privilege(s) | SELECT privilege  | Role assigned to service account has to contain: bigquery.jobs.create and bigquery.tables.getData for tables or bigquery.dataViewer role |  SELECT privilege | 
|  **Accessing to metadata**  | SELECT on INFORMATION_SCHEMA SCHEMA privilege  |  SELECT privilege | bigquery.metadataViewer role |  SELECT on INFORMATION_SCHEMA SCHEMA privilege |


| &nbsp;| Microsoft Fabric | Azure Synapse Analytics  | Vertica|
|:-:|:-:|:-:|:-:|
| **Connecting to remote database** | Read (default) permission | CONNECT permission | No privilege required |
| **Creating tables** | CREATE TABLE ON DATABASE (warehouse) and ALTER ON SCHEMA | CREATE TABLE permission | CREATE ON SCHEMA privilege |
| **Creating indexes** | N/A | ALTER permission | N/A |
|  **Creating functions**  | N/A | CREATE FUNCTION permission | CREATE ON SCHEMA privilege |
| **Creating procedures** | CREATE PROCEDURE ON DATABASE (warehouse) and ALTER ON SCHEMA  | CREATE PROCEDURE permission | CREATE ON SCHEMA privilege |
| **Removing objects (tables, indexes, functions, procedures)** | ALTER ON SCHEMA | ALTER permission | owning the object or DROP privilege on object |
| **Monitoring executions**  | Workspace Contributor or above permissions (queryinsights.exec_requests_history)  | CONTROL permission | No privilege required to use EXPLAIN statement |
|  **Writing data** | INSERT and/or UPDATE ON OBJECT | INSERT and UPDATE permissions | INSERT and UPDATE privileges |
| **Loading data into tables** | SELECT ON OBJECT and INSERT ON OBJECT| CREATE TABLE, EXECUTE, SELECT, INSERT, UPDATE, ALTER permissions | INSERT privilege on table, USAGE privilege on schema |
| **Accessing to client data** | SELECT ON OBJECT  | SELECT permission | SELECT privilege |
|  **Accessing to metadata**  | SELECT ON INFORMATION_SCHEMA | No permission required to describe table | USAGE ON SCHEMA, SELECT on TABLE and also privileges on tables v_catalog.columns and v_catalog.view_columns|
