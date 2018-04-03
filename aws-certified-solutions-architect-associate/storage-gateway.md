Storage Gateway
===============

Provides a service that connects an on-premises software appliance with cloud-based storage. AWS Storage Gateway's software appliance download as a VM image.

Four Types of Storage Gateway:
------------------------------

-	File Gateway(NFS): flat files
-	Volumes Gateway(iSCSI)
	-	Stored Volumes
	-	Cached Volumes

File Gateway(NFS)
-----------------

Files are stored as objects in your S3 buckets, accessed through a Network File System(NFS) mount point. Ownership, Permissions, and timestamps are durably stored in S3 in the user-metadata of the obejct associated with the file. Once objects are transferred to S3, they can be managed as native S3 objects, and bucket policies such as versioning, lifecycle management, and cross-region repliscation apply directly to objects stored in your bucket

Volume Gateway
--------------

The volum interface presents your applications with disk volumes using the iSCSI block protocol. Thinks as virtual hard disk. Data written to to these volumes can be asynchronously backed up as point-in-time snapshots of your volumes, and stored in the cloud as Amazon EBS(Elastic Block Store) snapshots. Snapshots are incremental backups that capture only changed blocks. All snapshot storage is also compressed to minimize your storage charges.

### Volume Gatway-Stored Volumes

Stored volumes let you store data locally, and then asynchronously copy that data to AWS as EBS snapshots. Pros: low-latency, 1GB - 16TB in size for Stored Volumes.

### Volumes Gateway-Cached volumes

Let you use S3 as your primary data storage.Locally only stores the most recent data, the rest data stores on S3 as EBS snapshots. Pros: low-latency, 1GB-32TB in size for Cached Volumes.

Volumes Gate-Tape Gateway
-------------------------

Exap Tips
---------

-	File Gateway: flat files, stored directly on S3
-	Volume Gateway-Store Volumes: Entire dataset is stored on site and is asynchronously backed up to S3.
-	Volume Gateway-Cached Volumes: Entire dataset is stored on S3 and the most frequently accessed data is cached on site.
-	Gateway Virtual Tape Library(VTL): Used for backup and uses popular backup applications like NetBackup, Backup Exec, Veeam etc
