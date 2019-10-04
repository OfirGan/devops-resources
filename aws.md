# AWS

## Cloud Practicioner

- [ ] **Cloud Computing**

  - [ ] What is cloud computing?

  - [ ] The 6 advantages of cloud computing
    - [ ] Trade capital expense for variable expense - pay for what you consume instead of investing in something you don't fully utilize
    - [ ] Benefit from massive economies of scale
    - [ ] Stop guess about capacity - Cloud scales with your needs
    - [ ] Increase speed and agility - You can use the cloud to quickly build platforms using architectures such as serverless for example
    - [ ] Stop spending money running and maintaining data centers - Focus on what you want instead of focusing on managing infrastructure
    - [ ] Go global in minutes - Easily deploy your application in multiple regions around the world which results in better experience (like lower latency) for users of your app

  - [ ] 3 Types of cloud computing
    - [ ] Infrastructure as a service (IAAS) - You are managing the server. It can virtual or physical. The provider (e.g. Amazon) will have no access to your server. EC2 is an example of IAAS.
    - [ ] Platform As a service (PAAS) - Someone else manages the underlying hardware and OS. You focus on the application side. Heroku and Google app engine are examples of PAAS.
    - [ ] Software As A service (SAAS) - You only worry about the software. As opposed to PAAS, you don't have to worry about the installation and the setup of the application. You just have to use the software itself.

  - [ ] 3 types of cloud computing deployments
    - [ ] Public Cloud - AWS, Azure & GCP
    - [ ] Hybrid - Mixture of public and private.
    - [ ] Private Cloud / On Premise - You manage it in your datacenter. OpenStack for example.
  
- [ ] **Global Infrastructure**
  
    - [ ] Availability Zone is one or more data centres, each with redundant power, networking and connectivity, housed in separate facilities.
    - [ ] Region is a geographical/physical area. Region consists of two or more availability zones
    - [ ] Edge locations are endpoints for AWS which are use for caching content.
    
- [ ] **IAM**
  
  - [ ] IAM (Identity Access Management) is global. You do not need to specify region when dealing with IAM related resources
  - [ ] There are 3 ways to access the AWS platform
  
    - [ ] Console
    - [ ] Programmatically(CLI)
    - [ ] Software Developers Kit (SDK)
  - [ ] Root account is the email address you to set up the AWS account and it has full permissions
  - [ ] Root account should not be given to anyone, instead the root account should create users
  
- [ ] **S3**

  - [ ] Simple Storage Service
  - [ ] S3 is a secure, highly scalable object based storage
  - [ ] S3 features:
      - [ ] Tiered Storage Available
      - [ ] Lifecycle Management - manage which storage tier the file you uploaded goes to
      - [ ] Versioning - managing different versions of your file and restore previous versions
      - [ ] Encryption
      - [ ] Security - using ACL (Access Control Lists) and bucket policies
  - [ ] S3 is object-based storage. The data itself is spread across multiple locations.
  - [ ] Files can be from 0 Bytes to 5 TB. There is unlimited storage.
  - [ ] Files are stored in buckets
  - [ ] Bucket name must be globally unique
      - [ ] For example: https://s3-eu-west-1.amazonaws.com/mybucket
  - [ ] HTTP 200 code is returned when a file is uploaded successfully to S3
  - [ ] Objects consist of:
      - [ ] Key - name of the object
      - [ ] Value - the data itself
      - [ ] Version ID - used for versioning
      - [ ] Metadata - data about the data
  - [ ] Data consistency
      - [ ] New objects - writing a new file, you will be able immediately read it
      - [ ] Overwrite and deletes - updating a file or deleting it, you may get the older version when reading it as changes to objects can take some time to be applied
  - [ ] Transfer Acceleration
      - [ ] when used, users will upload a file to the edge location which will then upload the files from edge locations to the bucket in specific location using optimized network path (Amazon internal network)
  - [ ] Cross Region Replication
      - [ ] For example: you have a bucket in Europe and you upload there a file from USA. This file will be replicated to USA region.
  - [ ] Charges
      - [ ] You are charged for the following: storage, requests, storage management, data transfer, transfer acceleration and cross region replication
  - [ ] Storage Classes
      - [ ] S3 standard - 99.99% availability and 11x9 durability
      - [ ] S3 IA - Infrequently access but rapid access when needed
      - [ ] S3 One Zone IA - lower cost option for IA without multiple AZ data resilience
      - [ ] S3 Intelligent Tiering -  ML based, designed to optimized costs by automatically moving to most cost-effective access tier
      - [ ] S3 Glacier - secure, durable and low-cost storage for data archiving
      - [ ] S3 Glacier Deep Archive - most lost cost storage class where a retrieval time of 12 hours is fine
  - [ ] Hosting a website
      - [ ] You can host static websites on s3
      - [ ] You cannot host dynamic websites on s3
      - [ ] s3 scales automatically to meet your website demands
  
- [ ] **EC2**

    - [ ] EC2 is Amazon Elastic Compute Cloud
        - [ ] Virtual servers in the cloud
    - [ ] Pricing models
        - [ ] On Demand - pay a fixed rate by the hour/second with no commitment
            - [ ] Good for:
                - [ ] users that want low cost and flexibility
                - [ ] applications with short terms, spiky or unpredictable workloads that cannot be interrupted
                - [ ] application being developed or tested for the first time
        - [ ] Reserved - you get capacity reservation
            - [ ] Contract terms: 1 year or 3 years. The longer, the cheaper
        - [ ] Spot - Enables you to bid whatever price you want for instances
            - [ ] when spot price hit your bid, you'll get the instance
            - [ ] when spot price is below your bid price, you'll lose the instance
        - [ ] Dedicated Hosts - physical EC2 server dedicated for your use

- [ ] **CloudFront**

    - [ ] What is CloudFront? a content delivery network (CDN) is a system of distributed servers that deliver web content to users based on the geographic location of:
        - [ ] the user
        - [ ] the origin of the web content
        - [ ] the content delivery server
    - [ ] Terminology
        - [ ] Edge location - the location where the content is cached
            - [ ] These location allow both read and write
        - [ ] Origin - The origin of the files which CDN will distribute (can be EC2 instance, S3 bucket, Elastic LB, ...)
        - [ ] Distribution - This name given the CDN (which consists of Edge locations)
    - [ ] How it works:
        - [ ] Users will try to query a file which happens to be on another geographic location.
        - [ ] Since it's not available in the edge location, they will get it from the origin location
        - [ ] The file which wasn't available in the edge location will now be stored at the edge location
        - [ ] Any future users will get it from the edge location in their area instead of going to the origin
    - [ ] Delivery Methods
        - [ ] Web Distribution - typically used for websites
        - [ ] RTMP - used for media streaming
    - [ ] Cache
        - [ ] objects are cached for the life of TTL in seconds
        - [ ] it's possible to clear cached objects but it's not free

    


## Questions

Name | Description
:------|:------:
[AWS interview questions and answers](https://www.besanttechnologies.com/aws-interview-questions-and-answers) | 250 AWS interview questions