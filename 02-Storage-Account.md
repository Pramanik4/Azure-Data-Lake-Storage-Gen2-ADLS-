# Azure Storage Account

## What is an Azure Storage Account?

An Azure Storage Account is an Azure service that acts as a central place to store and manage data in Azure.

Before creating services like Azure Blob Storage or Azure Data Lake Storage Gen2 (ADLS Gen2), we first need to create a Storage Account.

Think of it as a house. Inside the house, we can use different storage services like Blob Storage, Azure Files, Queue Storage, and Table Storage. If Hierarchical Namespace (HNS) is enabled, Blob Storage becomes Azure Data Lake Storage Gen2.

### Real-World Example

Imagine you are building an e-commerce application.

Customers upload product images, invoices, and order reports every day.

Before storing these files, you first create an Azure Storage Account.

Inside that Storage Account, you create a Blob Container or enable ADLS Gen2 to store the files securely.

### Architecture

Azure Subscription (It's like your electricity bill)
        │
        ▼
Resource Group      (Project folder)
        │
        ▼
Storage Account     (Container)
        │
 ┌──────┼──────────┬─────────┐
 │      │          │         │
 ▼      ▼          ▼         ▼
Blob   Files     Queues    Tables
               (ADLS Gen2 uses Blob)

> **Think of a Resource Group as a project folder.**

All the resources required for a project (like ADLS, Azure Data Factory, Azure Databricks, Azure Synapse Analytics, Key Vault, etc.) are kept inside a Resource Group.

If, after a few years, the project is no longer required, you don't have to delete each resource separately. Simply delete the Resource Group, and all the resources inside it will be deleted.

## Why do we need an Azure Storage Account?

We need an Azure Storage Account because it is the place where all Azure storage services are hosted and managed.

Inside a Storage Account, we can use services like Azure Blob Storage, Azure Files, Queue Storage, and Table Storage. If Hierarchical Namespace (HNS) is enabled, Blob Storage becomes Azure Data Lake Storage Gen2 (ADLS Gen2).

Without creating a Storage Account, we cannot create or use Azure Blob Storage or ADLS Gen2.

### Real-World Example

Imagine you're building an e-commerce application.

You need to store:
- Product images
- Customer invoices
- Application logs
- Backup files

Instead of creating separate storage services for each, you first create one Storage Account. Inside it, you can use Azure Blob Storage or enable ADLS Gen2 to store and manage all this data securely.

> 💡 **Interview Tip:** A Storage Account is mandatory because it acts as the parent resource for all Azure storage services. Without creating a Storage Account, you cannot create Blob Storage, Azure Files, Queue Storage, Table Storage, or ADLS Gen2.

## Components of an Azure Storage Account

An Azure Storage Account provides different storage services to store different types of data.

The four main storage services are:

- **Azure Blob Storage** – An object storage service that can store structured, semi-structured, and unstructured data such as CSV, JSON, Parquet, images, videos, PDFs, backups, and log files.
- **Azure Files** – Provides managed file shares that can be accessed by multiple users or applications over SMB or NFS. It is commonly used to share files like Excel sheets, Word documents, PDFs, CSVs, and other business files across different machines.
- **Azure Queue Storage** – Stores messages between different applications or services for asynchronous communication.
- **Azure Table Storage** – Stores large amounts of NoSQL structured data in a key-value format.
