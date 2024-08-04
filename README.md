# Bucket-Versioning-and-Replication

## SUMMARY

In this project, we explore Bucket versioning and replication to get an insight into how S3 bucket objects can be managed.
We will show how versioning maintains multiple versions of a file and also previous version's history.

There are different replication options on Amazon, viz: S3 Same-Region Replication (SRR), S3 Cross-Region Replication (CRR), S3 Replication Time Control (RTC).

For this project, we will configure Cross-Region Replication to replicate objects to a different region, create two different buckets with different regions, one the source bucket and the other the destination bucket. 

We will enable versioning for the two buckets created, create an IAM role to give the right permissions to read and replicate objects from the source bucket to the destination bucket and upload objects to the source bucket to observe the effect of versioning.

Finally, we will test versioning and replication to verify that objects uploaded are replicated in the destination region.

### STEP 1

* Create an S3 bucket

We navigate to S3 dashboard on AWS console and click create bucket to configure S3 bucket. Here we name the bucket "staticbucket456"

![alt text](<Images/Image 1.PNG>)

### STEP 2

* Enable Versioning

We enable bucket versioning on the bucket by navigating to "versioning section" in properties.

![alt text](<Images/Image 2.PNG>)

### STEP 3

* Configure Cross-Region Replication

This we achieved by navigating to management tab and select Replication.

![alt text](<Images/Image 3.PNG>)

we configure Cross-Region replication to replicate objects to a different region, creating two different buckets with different regions, the source bucket and the destination bucket. Also we create an IAM role for replication.

![alt text](<Images/Image 4.PNG>)

STEP 4

* Test Versioning 

To test our versioning setup, first we upload an object into the source bucket, edited the object and observe the effect of versioning.



![alt text](<Images/Image 6.PNG>)

S3 generates a version ID for each version and updates the bucket with the latest version while retaining the previous version of the file.

![alt text](<Images/Image 7.PNG>)

![alt text](<Images/Image 8.PNG>)


### STEP 5

* Test Replication

After bucket replication is configured, we observe that  the above objects from source bucket is automatically replicated in the destination region as well as new versions.