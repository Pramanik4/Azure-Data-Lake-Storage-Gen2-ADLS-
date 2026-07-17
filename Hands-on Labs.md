## Hands-on Lab 01 – Create Azure Data Lake Storage Gen2

### In search bar type "Storage Account & Click
<img width="1233" height="358" alt="image" src="https://github.com/user-attachments/assets/84a920ff-e0f3-4de5-8e46-b71a5c9aaf1d" />

#### Click on Create +
<img width="1625" height="792" alt="image" src="https://github.com/user-attachments/assets/65c6cff3-0953-44af-9604-200d5005ff95" />

#### Create a Resource Group, Storage Account , Select Region / Performance / Redundancy
<img width="1305" height="915" alt="image" src="https://github.com/user-attachments/assets/d90540b3-1459-42bc-bbea-4bf6ec1be8bf" />

#### Enable Hierarchical Namespace & Select Access Tier
<img width="1383" height="752" alt="image" src="https://github.com/user-attachments/assets/6d5af3b9-0154-442f-962f-99cd72258ab2" />

#### Click on Review + Create
<img width="992" height="427" alt="image" src="https://github.com/user-attachments/assets/dbb4fb69-3371-4077-a483-7b20b3556c8e" />

#### Created
<img width="1492" height="533" alt="image" src="https://github.com/user-attachments/assets/2f514a2f-f720-4994-a918-becc7e13d031" />

#### Now create a Container
<img width="1140" height="702" alt="image" src="https://github.com/user-attachments/assets/66f41728-ed87-4358-ac11-ef644d396a21" />

<img width="1761" height="905" alt="image" src="https://github.com/user-attachments/assets/7459d23f-e7e0-4f96-b64e-d263ce3135f4" />

#### Upload files in Bronze Container
<img width="1918" height="577" alt="image" src="https://github.com/user-attachments/assets/19774e62-9bfc-44de-9624-855a5d36d172" />

#### Rename a folder name from cutomer to cutomers
<img width="1052" height="472" alt="image" src="https://github.com/user-attachments/assets/4ccc7aba-2286-476f-81d1-2c4c801f3ee8" />

### What I Learned

- Created an ADLS Gen2 Storage Account.
- Enabled Hierarchical Namespace (HNS).
- Created a Container.
- Created folders inside the Container.
- Uploaded CSV files.
- Verified that folder rename works efficiently because of HNS.

### Try Out
Rename a Directory
Rename a File
Download a File
Delete a File
Delete a Directory

### Break Lease

**Break Lease** is used to lock a file so that no one can modify or delete it while it is being used by an application or process.

A file has a **Lease Status**.

- **Leased** → The file is locked, so other users or applications cannot modify or delete it.
- **Broken** → The lock is removed, so anyone with the required permissions can modify or delete the file.

For example, if an Azure Data Factory pipeline is writing data to a file, it may acquire a lease to prevent other processes from changing the file until the operation is complete.

## Hands-on Lab 2 - Understand the Medallion Architecture
#### Step 1 : Created 3 Containers bronze, silver and gold
<img width="1787" height="688" alt="image" src="https://github.com/user-attachments/assets/1fc8a35a-01aa-49f8-af73-58bae9c4597e" />

#### Step 2: Created folders in each container
<img width="1918" height="557" alt="image" src="https://github.com/user-attachments/assets/2800d34f-1587-464c-a957-c74d128f0fe5" />

#### Step 3: In bronze container inside respective folder upload files

<img width="442" height="492" alt="image" src="https://github.com/user-attachments/assets/66a56d7d-40aa-423d-96fd-b79d86205cc0" />

## Hands-on Lab 3 - Azure Data Factory (ADF)

#### Step 1 - Create Azure Data Factory
Search for Azure Data Factory & Select Data Factories (v2) 
Fill up the details

<img width="927" height="863" alt="image" src="https://github.com/user-attachments/assets/ca0ca028-f4c6-4a29-9b85-4d07365249de" />
Created & than Launch Studio

<img width="1217" height="518" alt="image" src="https://github.com/user-attachments/assets/26f4d07b-4da8-4217-b308-1a0490f7bf32" />

Azure Data Factory Interface
<img width="1683" height="651" alt="image" src="https://github.com/user-attachments/assets/a3194a97-f468-4dfa-a92f-887010e45ad2" />

ADF (Author) - The development area where you build ETL pipelines.
<img width="677" height="477" alt="image" src="https://github.com/user-attachments/assets/960e743a-c4c8-4ca7-8373-c4a47dea3153" />

ADF (Monitor) - The dashboard to monitor your pipelines.
<img width="1692" height="541" alt="image" src="https://github.com/user-attachments/assets/e1e59d00-a031-4107-8871-561ea5cb1be2" />

ADF (Manage) - The settings page for ADF.
<img width="1486" height="917" alt="image" src="https://github.com/user-attachments/assets/fde838e9-1ec3-47f7-9310-5309fbedae40" />

#### Create Linked Service
Step 1: Go to manage than Linked Service & than fill all details

<img width="1688" height="908" alt="image" src="https://github.com/user-attachments/assets/1864d92c-ae0e-44bb-8320-5b9a0670d487" />

## Hands-on Lab 5 - Create a Dataset

What is Dataset?

A Dataset represents the data (file, table, or folder) that Azure Data Factory reads from or writes to. It uses a Linked Service to connect to the actual data source.

<img width="1918" height="866" alt="image" src="https://github.com/user-attachments/assets/46b1f984-3738-423c-97ca-02a8c9ea98d6" />

<img width="1918" height="818" alt="image" src="https://github.com/user-attachments/assets/a13ca0e7-728f-4086-92ad-990bb1b74736" />

## Hands-on Lab 6 - Create Your First Pipeline

**NOTE: 
To create Linked Service -> Manage
To create Dataset -> Author**

### Interview Question

#### Q What is Break Lease in Azure Storage?
#### Q Why do we select "Import schema = None" for the Sink Dataset?
#### Q When would you use sequential execution instead of parallel execution in Azure Data Factory?
#### Q Why should we use parallel execution for independent activities?











