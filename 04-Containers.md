# Containers

## What is a Container?

A Container is a logical storage unit inside an Azure Storage Account.

It is used to organize and store data such as CSV, JSON, Parquet, images, videos, PDFs, and other files.

Before uploading data to Azure Blob Storage or ADLS Gen2, we first need to create a Container.

### Simple Architecture

<img width="236" height="416" alt="image" src="https://github.com/user-attachments/assets/be5f0ab2-575a-40fe-973e-786fc5fcbf8e" />

### Real-World Example

Suppose an e-commerce company has a Storage Account named **companydata**.

Inside the Storage Account, it creates different Containers to organize data.

```
companydata
│
├── raw-data
├── processed-data
├── backup
└── logs
```

Each Container stores a different type of data, making it easier to organize and manage information.

## Why do we need Containers?

We need Containers to organize different types of data separately.

For example, a company may have customer data, order data, application logs, product images, and backup files. Instead of storing everything in one place, we can create separate Containers for each type of data.

This makes it easier to manage, find, secure, and process the data whenever required.

## Container vs Folder

A Container is the top-level storage unit inside a Storage Account, whereas a Folder is used to organize files inside a Container.

A Storage Account can have multiple Containers, and each Container can have multiple Folders (only in ADLS Gen2 with Hierarchical Namespace enabled).

| Container                                | Folder                                   |
| ---------------------------------------- | ---------------------------------------- |
| Top-level storage unit                   | Organizes files inside a Container       |
| Created inside a Storage Account         | Created inside a Container               |
| Can have multiple folders                | Can have subfolders and files            |
| Used to separate different types of data | Used to organize data within a Container |

### Real-World Example

<img width="287" height="362" alt="image" src="https://github.com/user-attachments/assets/79642d62-816e-4d1e-8a61-2c39883a30bb" />

## Container vs Storage Account

A Storage Account is the main Azure resource that hosts storage services like Blob Storage, Azure Files, Queue Storage, and Table Storage.

A Container is a logical storage unit created inside a Storage Account to organize and store data.

### Interview Questions
#### Q1. What is the difference between a Container and a Folder?

#### Q2. Can a Storage Account have multiple Containers?

#### Q3. Can a Container have multiple Folders?

#### Q4. Can a Folder exist without a Container?

#### Q5. In ADLS Gen2, where are files stored?

#### Can we upload a file directly into a Storage Account without creating a Container?

