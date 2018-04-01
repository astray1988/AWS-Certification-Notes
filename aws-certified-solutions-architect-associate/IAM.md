#Identify Access Management

IAM capabilities:
-----------------

-	Centralized control of AWS account
-	Shared Access to AWS account
-	Granular Permissions
-	Identity Federation,which means connect IAM to your Activate Directory, Facebook and Linkedin etc
-	Multifactor Authentication
-	Provide temporary access for users/devices and services where necessary
-	Allows to set up your own password rotation policy
-	Integrated with many different AWS services
-	Supports PCI DSS Compliance

Critical Terms:
---------------

-	Users - End Users, aka people
-	Groups - A collection of users under one set of permissions.
-	Roles - You create roles and can then assign AWS them to AWS resources
-	Policies - A document that defines one or more permissions
-	MFA(Multi-factor authentication account)

Labs:
-----

Learnt:
-------

-	IAM is universal. It does not apply to regions at this time. The "root account" is simply the account created when first setup your AWS account. It comes with complete Admin access. - New Users have NO permissions when first created.
-	New Users are assigned ACCESS KEY ID & SECRET ACCESS KEYS when first created. You canno use ACCESS KEY ID & SECRET ACCESS KEYS login to AWS console. You can use this to access AWS via the APIs and Command Line.
-	You only get to view these once. If you lose them, you have to regenerate them. So you need save them in a secured location.
-	You can create and customized your own password rotation policy.
