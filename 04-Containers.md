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

