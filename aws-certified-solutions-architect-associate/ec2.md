EC2
===

Know the differences between: - On Demand - Spot - Reserved - Dedicated Hosts

Remember with spot instance: - If you terminate the instance, you pay for the hour - If AWS terminates the spot instance, you get the hour it was terminated in for free.

EBS Consists of:
----------------

-	SSD, Gereral Purpose
-	GP2 - (Up to 10,000 IOPS)
-	SSD, Provisioned IOPS -IO1 - (More than 10,000 IOPS)
-	HDD, Throughput Optimized
-	ST1 - frequently accessed workloads
-	HDD, Cold - SC1 - less frequently accessed data
-	HDD, Magnetic
-	Standard - cheap, infrequently accessed Storage

You cannot mount 1 EBS volume to multiple EC2 instances, instead use EFS.

EC2 Instance Types: DR MC GIFTPX - D for Density - R for RAM - M -main choice for general purpose applications - C for compute - G for Graphics - I for IOPS - f for FPGA - T for cheap general purpose, e.g, T2 Micro - P for Graphics - X for Extreme Memory,

Lab summary
-----------

-	Termination Protection is turned off by default, you must turn it on.
-	On an EBS-backed instance, the default action is far the root EBS volume to be deleted when the instance is terminated
-	EBS Root Volumes of your DEFAULT AMI's cannot be encrypted. You can also use a third party tool e.g. bit locker, to encrypt the root volume, or this can be done when creating AMI's in the AWS console or using the API.

Security Group Lab
------------------

-	All inbound Traffic is Blocked by DEFAULT
-	All outbound traffic is Allowed
-	Changes to Security Groups take effect immediately
-	You can have any number of EC2 instances within a security group.
-	You can have multiple security groups attached to EC2 instances
-	Security groups are stateful
	-	If you create an inbound rule allowing traffic in, that traffic is automatically allowed back out again. You cannot block specific IP addresses using Security Groups, instead use Network Access Control Lists.

Volumes & Snapshots
-------------------

-	Volumes exist on EBS: Virtual Hard disk
-	Snapshots exist on S3.
-	Snapshots are point in time copies of Volumes.
-	Snapshots are incremental, which means that only the blocks that have changed since your last snapshot are moved to S3.
-	To create a snapshot for Amazon EBS volumes that serve as root devices, you should stop the instance before taking the snapshot.
-	You can take a snapshot when the instance is running.
-	To move an EC2 volume from on AZ/Region to another AZ/Region, you just need take a snapshot or an image of it, then copy it to the new AZ/Region.
-	Snapshots of encrypted volumes are encrypted automatically.
-	Volumes restored from encrypted snapshots are encrypted automatically.
-	You can share snapshots, but only if they are unencrypted.
	-	These snapshots can be shared with other AWS accounts or made public.

Volumes & Snapshots - Security
------------------------------

-	Snapshots of encrypted volumes are encrypted automatically.
-	Volumes restored from encrypted snapshots are encrypted automatically.
-	You can share snapshots, but only if they are unencrypted.

AMI Types(EBS vs Instance Store)
--------------------------------

Select your AMI based on: 1. Region 2. Operating system 3. Architecture(32-bit or 64-bit) 4. Launch Permissions 5. Storage for the Root Device(Root Device Volume) 6. Storage for the Root Device(Root Device Volume): - Instance Store(Ephemeral Stroage) - EBS Backed Volumes

EBS vs Instance Store
---------------------

All AMIs are categorized as either backed by Amazon EBS or backed by instance store.

For EBS volumes: The root device for an instance launched from the AMI is an Amazon EBS volume created from an Amazon EBS snapshot.

For Instance Store volumes: The root device for an instance launched from the AMI is an instance store volume created from a template stored in Amazon S3.

EBS vs Instance Store - Exam Tips
---------------------------------

-	Instance Store Volumes are sometimes called Ephemeral Storage.
-	Instance store volumes cannot be stopped. If the underlying host fails, you will lose your data.
-	EBS backed instances can be stopped. You will not lose the data on this instance if it is stopped.
-	You can reboot both, you will not lose your data.
-	By default, both ROOT volumes will be deleted on termination, however with EBS volumes, you can tell AWS to keep the root device volume.

Elastic Load Balances
---------------------

-	Instances montiored by eLB are reported as: inSerivce or outOfService
-	Health checks check the instance health by talking to it.
-	Have their own DNS name. You are never given an IP address.
-	Read the ELB FAQ for Class Load Balancers.

CloudWatch
----------

-	Standard Monitoring = 5 minute; Detailed Monitoring = 1 minute
-	Dashboards: See what is happening with your AWS environment
-	Alarms: Allows to set alarms that notify you when particular thresholds are hit.
-	Events: respond to state changes in your AWS resources
-	Logs: aggregate, monitorm and store logs. Need install agents on EC2 server.
