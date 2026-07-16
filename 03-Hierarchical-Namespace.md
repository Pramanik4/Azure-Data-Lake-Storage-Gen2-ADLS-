# Hierarchical Namespace (HNS)

## What is Hierarchical Namespace?

Hierarchical Namespace (HNS) is a feature in Azure Data Lake Storage Gen2 that organizes data into a real folder and file structure, similar to the file system on your computer.

It allows files and folders to be managed efficiently, making operations like renaming, moving, and deleting directories much faster compared to Azure Blob Storage.

HNS is the key feature that converts Azure Blob Storage into Azure Data Lake Storage Gen2.

### Simple Example

My Laptop

Documents
│
├── Project A
│      ├── sales.csv
│      └── customers.csv
│
└── Project B
       └── orders.csv

## Why was Hierarchical Namespace (HNS) introduced?

### The Problem

Azure Blob Storage uses a flat namespace where folders are virtual.

Suppose we have the following structure:

raw-data/
├── file1.csv
├── file2.csv
├── ...
└── file10000.csv

If the company wants to rename the folder **raw-data** to **bronze-data**, Azure Blob Storage cannot simply rename the folder because it doesn't actually exist as a real directory.

Instead, Azure has to update the path of every file (effectively copying them to the new path and deleting the old ones). If there are thousands or millions of files, this operation becomes slow and expensive.

### The Solution

ADLS Gen2 introduces Hierarchical Namespace (HNS), where folders are real directories instead of virtual ones.

Now, when we rename **raw-data** to **bronze-data**, only the directory metadata is updated. Azure doesn't need to rename every individual file, making the operation much faster and more cost-effective.

## Flat Namespace vs Hierarchical Namespace

In Azure Blob Storage, folders are virtual and do not actually exist. The complete path is stored as part of the blob name.

For example:

Here, `sales`, `2026`, and `July` are not real folders. They are just part of the blob's name.

Because of this, operations like renaming or moving a folder require updating the path of every file inside that folder, which becomes slow and expensive when dealing with large amounts of data.

In ADLS Gen2, folders are real directories just like the folders on a computer.

For example:

Since folders actually exist, operations like renaming, moving, or deleting directories are much faster because Azure only updates the directory metadata instead of modifying every file.

| Flat Namespace (Blob Storage)      | Hierarchical Namespace (ADLS Gen2)        |
| ---------------------------------- | ----------------------------------------- |
| Virtual folders                    | Real folders                              |
| Full path is part of the blob name | Folder structure is maintained separately |
| Rename is slow                     | Rename is fast                            |
| Move is expensive                  | Move is efficient                         |
| Best for object storage            | Best for Big Data Analytics               |

## Real-World Example

Imagine an e-commerce company stores daily sales data like this:

bronze/
├── Jan/
├── Feb/
├── Mar/

After a few months, the company decides to rename **bronze** to **raw**.

- In Azure Blob Storage, Azure has to update the path of every file because folders are virtual.
- In ADLS Gen2, Azure simply updates the directory metadata because folders are real.

This makes rename operations much faster and more cost-effective in ADLS Gen2.

## Key Takeaways

- Hierarchical Namespace (HNS) is the core feature of ADLS Gen2.
- HNS provides a real folder and file structure.
- Azure Blob Storage uses a flat namespace with virtual folders.
- Rename, move, and delete operations are much faster in ADLS Gen2.
- HNS is one of the main reasons ADLS Gen2 is preferred for Big Data Analytics.

### Interview Questions

#### Q2. Why was Hierarchical Namespace introduced?

#### Q3. What is the difference between Flat Namespace and Hierarchical Namespace?

#### Q4. Why are rename operations faster in ADLS Gen2 than in Azure Blob Storage?

#### Q5. What is the biggest difference between Azure Blob Storage and ADLS Gen2?

#### Q6. Can ADLS Gen2 exist without Hierarchical Namespace?

#### Q7. What happens if Hierarchical Namespace is not enabled in a Storage Account?
