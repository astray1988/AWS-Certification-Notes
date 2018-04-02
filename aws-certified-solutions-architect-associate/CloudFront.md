CloudFront
==========

A content delivery network(CDN) is a system distributed servers that deliver webpages and other web content to a use based on the geographic locations of the user, the origin of the webpage and a content deliver server.

Amazon CloudFront can be used to deliver your entire website, including dynamic, static, streaming, and interactive content using a global network of edge locations. Requests for your content are automatically routed to the nearest edge location, so content is delivered with the best possible performance.

Amazon

Key Terminology
---------------

-	Edge Location: This is the location where content will be cached. This is separate to an AWS Region/AZ
-	Origin: This is the origin of all the files that the CDN will distrubte. This can be either an S3 bucket, an EC2 instance, an Elastic Load Balancer or Route53.
-	Distrubution: This is the name given the CDN which consists of a collection of Edge Locations.
-	Web Distribution: Typically used for websites.
-	RTMP - Used for Media streaming
-	Edge locations are not just READ only, you can write to them too. e.g. put an object on to them.
-	Objects are cached for the life of the TTL(Time to Live)
