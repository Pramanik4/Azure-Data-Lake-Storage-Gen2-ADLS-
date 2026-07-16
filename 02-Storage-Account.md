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

## Types of Azure Storage Accounts

| Storage Account Type      | Description                                                                       |
| ------------------------- | --------------------------------------------------------------------------------- |
| General Purpose v2 (GPv2) | Recommended Storage Account. Supports Blob, ADLS Gen2, Files, Queues, and Tables. |
| General Purpose v1 (GPv1) | Older version. Limited features and not recommended for new projects.             |
| Blob Storage              | Optimized only for Blob Storage. Legacy account type.                             |
| BlockBlobStorage          | Premium performance for block blobs. Used for high-performance workloads.         |
| FileStorage               | Premium storage account used only for Azure Files.                                |

### Which Storage Account should we use?

For almost all modern Azure Data Engineering projects, **General Purpose v2 (GPv2)** is the recommended Storage Account because it supports:

- Azure Blob Storage
- Azure Data Lake Storage Gen2 (by enabling HNS)
- Azure Files
- Queue Storage
- Table Storage

It also supports the latest Azure features, better security, lifecycle management, and performance improvements.

### Real-World Example

Suppose you're building a modern Data Engineering solution.

You need:
- Store raw data in ADLS Gen2
- Process data using Azure Databricks
- Load data using Azure Data Factory
- Query data using Azure Synapse Analytics

In this case, you would create a **General Purpose v2 (GPv2)** Storage Account because it supports all the required storage services and features.

> 💡 **Interview Tip:** If an interviewer asks, "Which Storage Account would you choose for ADLS Gen2?", the answer is **General Purpose v2 (GPv2)** with Hierarchical Namespace (HNS) enabled.

## Standard vs Premium Storage

When creating a Storage Account, Azure asks us to choose the performance tier.

The two available options are:

- Standard
- Premium

The performance tier determines how the data is stored, the speed at which it can be accessed, and the overall cost.

### Standard Storage

Standard Storage uses Hard Disk Drives (HDDs) to store data.

It is a cost-effective option and is suitable for most workloads where ultra-fast performance is not required.

It is commonly used for:
- Azure Blob Storage
- Azure Data Lake Storage Gen2
- Backups
- Logs
- Data Engineering workloads

### Premium Storage

Premium Storage uses Solid State Drives (SSDs), which provide much faster read and write performance than HDDs.

It is designed for workloads that require low latency and high IOPS.

It is commonly used for:
- Virtual Machines
- Azure Files requiring high performance
- Databases
- High-performance applications

### Real-World Example

Imagine Netflix stores 5 PB of movies and user logs.
Do they need SSD for all of it?
No.

Most of that data is simply stored and read later for analytics.
So they use Standard Storage because it's much cheaper.
Now think about a banking application processing thousands of transactions every second.
The database serving those transactions needs very fast reads and writes.
That's where Premium Storage is useful.

> 💡 **Interview Tip:** For Azure Data Engineering projects using ADLS Gen2, Standard performance is the most common choice because it provides sufficient performance at a much lower cost.

## Data Redundancy (Replication)

Data Redundancy means Azure stores multiple copies of our data so that it remains safe even if a hardware failure, server failure, or an entire data center becomes unavailable.

Instead of keeping only one copy of the data, Azure automatically creates multiple copies based on the redundancy option we choose.

This helps ensure high availability, durability, and disaster recovery.

### Real-World Example

Suppose a bank stores all customer transaction data in Azure Storage.

If a server suddenly crashes, customers should still be able to access their account information.

Azure achieves this by keeping multiple copies of the data, ensuring that another copy is available even if one copy becomes unavailable.

### Key Takeaways

- Redundancy means storing multiple copies of data.
- It protects data from hardware and data center failures.
- It improves data availability and durability.
- Azure provides different redundancy options based on business requirements.

### Azure Storage redundancy options

#### 1. LRS (Local)
Mumbai Data Center

Copy 1
Copy 2
Copy 3

👉 Everything stays inside one data center.

#### 2. ZRS (Zone)
Mumbai Region

Zone 1 → Copy 1
Zone 2 → Copy 2
Zone 3 → Copy 3
👉 Copies are spread across different Availability Zones in the same region.

#### 3. GRS (Geo)
Primary Region (Mumbai)

Copy 1
Copy 2
Copy 3
        ↓
Secondary Region (Chennai)

Copy 4
Copy 5
Copy 6
👉 Azure also keeps another 3 copies in a paired region.

#### 4. RA-GRS

Same as GRS, but:
✅ You can read data from the secondary region even if the primary region is still running.

#### 5. GZRS
Primary Region

Zone 1
Zone 2
Zone 3
        ↓
Secondary Region

3 more copies
👉 Combines ZRS + GRS.

#### 6. RA-GZRS

Same as GZRS, plus:

✅ Read access from the secondary region.

### Memory Trick

LRS = Local copies
ZRS = Zone copies
GRS = Geo copies
RA-GRS = Geo copies + Read Access
GZRS = Zone + Geo copies
RA-GZRS = Zone + Geo + Read Access

