---
tags:
  - system-design
type: permanent
related: "[[distributed systems]]"
---
In a **file storage** service.
example services: Elastic File System and google file store
DataStructure:
    - Data is stored in a hierarchical structure (folders and files), similar to how data is organized in traditional file systems.
    - Uses the **NFS protocol**, making it accessible from other compatible environments.
Access and Use Case
- **EFS** can be used when you need shared access to a **file system** across multiple EC2 instances or when applications require standard file system access (like mounting directories).
    - Use Cases: Web serving, content management, file sharing, home directories, etc.
    - It’s ideal for **POSIX-compliant** workloads, which require file system semantics (like permissions and file locks).
Scalability:
- file storage like EFS is automatically scalable and adjusts to the size of your data. It provides high availability and can scale up to petabytes of data.
    - Designed for **low-latency** access to a shared file system.
Access Method
file storage like **EFS** can be mounted directly onto EC2 instances as a **file system** using standard file system commands like `mount`. It can also be accessed from on-premises environments through **AWS Direct Connect** or **VPN**.
### Performance
- **EFS** offers high throughput and low-latency performance for use cases requiring frequent read/write access to files. It supports **concurrent access** from thousands of EC2 instances.

In an **object storage** service.
DataStructure:
- Data is stored as **objects** within **buckets**. Each object consists of data, metadata, and a unique identifier.
- There is no file hierarchy in S3. Files are organized by object keys (which can look like a folder structure but isn't a true hierarchy).
- example services: S3 and Google Cloud object storage
Access and Use Case
- **S3** is used for storing **large volumes** of data and can be accessed over the internet via HTTP/HTTPS or programmatically through APIs.
    - Use Cases: Backup and archival, data lakes, media storage, big data analytics, and cloud-native applications.
    - It’s ideal for storing **unstructured data** such as logs, backups, images, or videos.    
Scalability:
- object storage like S3 is highly scalable as well but in terms of object storage. You can store **unlimited** amounts of data across many geographic regions. It is designed for storing massive amounts of data that need to be accessed with higher latency and lower throughput compared to file storage systems.

 **Access Methods:**    
- object storage like **S3** is accessed through **APIs**, SDKs, or via HTTP/HTTPS. Files are accessed by unique object keys instead of file paths, which gives more flexibility but less traditional file system behavior.
Performance
- **S3** has **higher latency** compared to file systems but can handle very high-throughput workloads with infrequent access patterns, particularly for large objects.
    - Great for **bulk storage** but not for workloads requiring rapid, frequent updates to files.