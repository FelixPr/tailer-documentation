---
description: >-
  Learn how to export data located in a BigQuery table into CSV files using a
  Table to Storage operation.
---

# Export data with Tables to Storage

## 💡 What is Table to Storage?

A Table to Storage \(TTS\) data pipeline operation allows you to export your data from a BigQuery table to a CSV file in a Google Cloud Storage bucket so you can leverage them with other tools, such as a warehouse management system.

## ✅ Supported file types

### **Databases**

* Google BigQuery

### **Export files**

* CSV file in Google Cloud Storage

## ⚙️ How it works

When the Table to Storage Tailer workflow is triggered by an event \(usually a BigQuery table update\):

* The SQL query you specify will be executed to extract the relevant data from the source BigQuery table.
* The data will be exported to a CSV file located in the GCS bucket you specified.

## **📋 How to deploy a Table to Storage data operation**

1. Access your **tailer** folder \(created during [installation](../../getting-started/install-tailer-sdk.md)\).
2. Create a working folder as you want, and create a JSON file for your data operation inside.
3. Create a [SQL file](table-to-storage-sql-file.md) to determine what data to extract.
4. Prepare your JSON configuration file. Refer to this page to learn about all the [parameters](table-to-storage-configuration-file.md).
5. Create a [Workflow configuration file](../orchestrate-processings-with-workflow/workflow-configuration-file.md) that will define how to trigger it.
6. Access your working folder by running the following command:

   ```text
   cd "[path to your working folder]"
   ```

7. To deploy the data operation, run the following command:

   ```text
   tailer deploy your-file.json
   ```

8. Log in to [Tailer Studio](https://jarvis-platform.io/sign-in?redirect=%2F&__hstc=57968821.199e85015347f5cf00c120e5932c4c81.1601276395705.1601454251429.1601460096069.15&__hssc=57968821.4.1601460096069&__hsfp=649433320) to check the status and details of your data operation.
9. For your workflow to be executed, you either need to run the data operation that is set to trigger it in your Workflow data operation \(previous step in your data pipeline\), or to launch it manually from [Tailer Studio](https://jarvis-platform.io/sign-in?&__hstc=57968821.199e85015347f5cf00c120e5932c4c81.1601276395705.1601454251429.1601460096069.15&__hssc=57968821.4.1601460096069&__hsfp=649433320).
10. Access the GCS bucket to check your output CSV file.

