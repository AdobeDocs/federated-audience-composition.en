---
title: Permissions for accessing an external database
description: Learn about rights specific to each database engine
exl-id: 287fb4a4-5767-4337-96be-dceca55f756d
---
# Federated Data Access (FDA) Rights matrix {#fda-rights}

The following table outlines the required database permissions for each system, letting you perform operations on external databases through federated data access (FDA).

| &nbsp;| Snowflake | Redshift | Google BigQuery | Databricks |
|:-:|:-:|:-:|:-:|:-:|
| **Connecting to remote database** | `USAGE ON WAREHOUSE`, `USAGE ON DATABASE`, and `USAGE ON SCHEMA` privileges | Create a user linked to the AWS account | Create a service account and grant principal access to project | `USE CATALOG` permission on Catalog and `CAN_USE` permission on SQL Warehouse |
| **Creating tables** | `CREATE TABLE ON SCHEMA` privilege | `CREATE` permission | Role assigned to service account has to contain: `bigquery.jobs.create` and `bigquery.tables.create` permissions | `USE SCHEMA` and `CREATE TABLE` permissions |
| **Creating indexes** | N/A | `CREATE` permission | BigQuery only supports search indexes. The role assigned to the service account has to contain: `bigquery.jobs.create`, `bigquery.tables.getData`, and `bigquery.tables.createIndex` permissions | N/A |
| **Creating functions** | `CREATE FUNCTION ON SCHEMA` privilege | `USAGE ON LANGUAGE plpythonu` permission to be able to call external Python scripts | The role assigned to service account has to contain: `bigquery.jobs.create` and `bigquery.routines.create` permissions | `CREATE FUNCTION` permission |
| **Creating procedures** | N/A | `USAGE ON LANGUAGE plpythonu` permission to be able to call external Python scripts | The role assigned to the service account has to contain: `bigquery.jobs.create` and `bigquery.routines.create` permissions | N/A | 
| **Removing objects (tables, indexes, functions, procedures)** | Owning the object | Owning the object or being a superuser | The role assigned to the service account has to contain: `bigquery.jobs.create`, `bigquery.routines.delete`, `bigquery.tables.delete`, and `bigquery.tables.deleteIndex` permissions | N/A |
| **Monitoring executions** | `MONITOR` privilege on the required object | No permissions required to use the `EXPLAIN` command | `monitoring.viewer` role | `CAN_VIEW` permission |
| **Writing data** | `INSERT` and/or `UPDATE` privileges (depending on the write operation) | `INSERT` and `UPDATE` permissions | The role assigned to the service account has to contain: `bigquery.jobs.create` and `bigquery.tables.updateData` | `MODIFY` permission | 
| **Loading data into tables** | `CREATE STAGE ON SCHEMA`, `SELECT`, and `INSERT` on the target table privileges | `SELECT` and `INSERT` permissions | The role assigned to the service account has to contain: `bigquery.jobs.create`, `bigquery.tables.getData`, and `bigquery.tables.updateData` | `SELECT` and `MODIFY` permissions | 
| **Accessing to client data** | `SELECT on (FUTURE) TABLE(S)` or `VIEW(S)` privilege(s) | `SELECT` permission | The role assigned to the service account has to contain: `bigquery.jobs.create` and `bigquery.tables.getData` for tables or the `bigquery.dataViewer` role | `SELECT` permission | 
| **Accessing to metadata** | `SELECT on INFORMATION_SCHEMA SCHEMA` privilege | `SELECT` permission | `bigquery.metadataViewer` role |  `SELECT on INFORMATION_SCHEMA SCHEMA` permission |


| &nbsp;| Microsoft Fabric | Azure Synapse Analytics | Vertica |
|:-:|:-:|:-:|:-:|
| **Connecting to remote database** | Read (default) permission | `CONNECT` permission | No privilege required |
| **Creating tables** | `CREATE TABLE ON DATABASE` (warehouse) and `ALTER ON SCHEMA` | `CREATE TABLE` permission | `CREATE ON SCHEMA` privilege |
| **Creating indexes** | N/A | `ALTER` permission | N/A |
| **Creating functions** | N/A | `CREATE FUNCTION` permission | `CREATE ON SCHEMA` privilege |
| **Creating procedures** | `CREATE PROCEDURE ON DATABASE` (warehouse) and `ALTER ON SCHEMA` | `CREATE PROCEDURE` permission | `CREATE ON SCHEMA` privilege |
| **Removing objects (tables, indexes, functions, procedures)** | `ALTER ON SCHEMA` | `ALTER` permission | Owning the object or the `DROP` privilege on object |
| **Monitoring executions** | Workspace Contributor or above permissions (`queryinsights.exec_requests_history`) | `CONTROL` permission | No privilege required to use `EXPLAIN` statement |
| **Writing data** | `INSERT` and/or `UPDATE ON OBJECT` | `INSERT` and `UPDATE` permissions | `INSERT` and `UPDATE` privileges |
| **Loading data into tables** | `SELECT ON OBJECT` and `INSERT ON OBJECT` | `CREATE TABLE`, `EXECUTE`, `SELECT`, `INSERT`, `UPDATE`, and `ALTER` permissions | `INSERT` privilege on table, `USAGE` privilege on schema |
| **Accessing to client data** | `SELECT ON OBJECT` | `SELECT` permission | `SELECT` privilege |
| **Accessing to metadata** | `SELECT ON INFORMATION_SCHEMA` | No permission required to describe table | `USAGE ON SCHEMA`, `SELECT on TABLE`, and also privileges on tables `v_catalog.columns` and `v_catalog.view_columns` |
