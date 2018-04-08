Databases
=========

Database Types:
---------------

-	RDS-OLTP
	-	SQL
	-	MYSQL
	-	PostgreSQL
	-	Oracle
	-	Aurora
	-	MariaDB
-	DynamoDB - No SQL
-	RedShift-OLAP, dataware housing
-	Elasticache: In memory caching
	-	Memcached
	-	Redis

### Multi-AZ

### Read Replica

### Aurora Scaling

-	2 copies of your data is contained in each AZ, with minimum of 3 AZs, 6 copies of your data

DynamoDB vs RDS
---------------

-	DynamoDB: scale the DB on the fly without down time.
-	RDS: not easy to scale, neither need to add bigger instance size or add a read replica.

DynamoDB
--------

-	Stored on SSD Storage
-	Spread on 3 geographically distinct data centers.
-	Eventual Consistent Reads(default):
-	Stringly Consistent Reads: write to DDB and can provision under 1s.

Redshift Configuration
----------------------

-	Single Node: 160 GB
-	Multi-Node:

	-	Leader Node: manages client connections and receive queries
	-	Compute Node: store data and perform queries and computations. Up to 128 Compute notes

Elasticache
-----------

-	Memcached

-	Redis

