Introduction

1. Question: What is Cloud?  
    Cloud is a Network or Internet. Is present on remote location and accessible only through the internet.

2. Question: What is Cloud Computing?  
    Cloud Computing means storing and accessing data and programs over the internet instead of your computer hardware. Can access Cloud Resources from anywhere in the world.

3. Question: Why is CloudTechnology booming?  
    High prices, a lot of manpower required for os, message, database, power supply, cabling, etc. Majority care by AWS.

4. Question: Benefits of Cloud?  
    Pay per usage, no upfront feeds, no hardware maintenance

5. Question: Regions?  
    AWS Cloud Computing are hosted in multiple locations. Locations are composed of AWS regions and availibility zones. If you pick bad region you have high latency. Region has multiple availability zones. If one availability zone fails another availability zone will handle request.

EC2

1. Question: What is EC2?  
    Elastic Cloud Computing. It is instance, operating system. Basically virtual server. Eliminates investing into hardware.

2. Question: EC2 Pricing Models On-Demand  
    Pay per hour or per second. Low cost and flexibility without any up front payment.

3. Question: EC2 Pricing Models Spot instance  
    Get EC2 instance at cheap (max 90% price discount) but you don't know you will receive the instance. Flexable start and end times. Can take 1 day to receive instance.

4. Question: EC2 Pricing Models Reserved instances  
    Pay in advance, applications with steady usage, need to commit for 1-3 years to reduce costs. Up to 75% cheaper than ondemand.

5. Question: EC2 Pricing Models Dedicated Hosts  
    Dedicated host is a phyisical ec2 server dedicated for your use.

6. Question: What is default setting of terminate protection?  
    By default it is turned OFF. You can enable it dashboard under actions and instance settings.

7. (IMPORTANT) Question: What is EBS?  
    Elastic Block Store is easy to use high perofrmance block storage services designed for use with EC2.

8. (IMPORTANT) Question: What happens to root EBS volume when you delete instance?  
8. It gets deleted.

9. (IMPORTANT) Question: How is EBS root volume encrypted?  
    It can't be encryped. You can use some third-party software to encrypt. You can encrypt additional volumes though.

10. Question: What is inbound and what is outbound in security group?  
    Inbound is traffic coming to my server, outbound is traffic going from my server.

11. Question: Default settings for security group.  
    By default no inbound traffic is allowed. All outbound traffic is allowed.

12. Question: What to we have to do for security group changes to take effect?  
    Changes are applied instantly. Nothing else required.

13. Question: How many security groups can be attached to one instance and how many instances can use same security group?  
    You can attach multiple security groups to one instance and use same security group in different instances. There are no limits.

14. Question: Exam tips security groups.  
    Security groups are STATEFUL, inbound rules are automatically allowing back out again,  you cannot block specific IP using SG, use NACL. You can specific allow rules, not deny rules.

15. Question: Can you encrypt root volume? How would you encrypt existing root volume?  
    Yes. Create snapshot of volume, then create instance of volume with encrypted.

16. Question: What is elastic IP?  
    It is a static / persistent public IP address for EC2 instance that will persist through stop, restart etc. It is reserved public IP address.

17. Question: What is CloudWatch?  
    CloudWatch is a service intended for monitoring AWS resources and the applications you run on AWS. Enables real time monitoring such as EC2 instances, RDS databases, load balanced, Route 53 etc.

18. Question: What can you do with CloudWatch?  
18. You can use CloudWatch to collect and track metric, collect and monitor log files, set alarms and automatically react to changes in AWS resources. CPU utilization, latency, request counts etc.

19. Question: Exam tips CloudWatch.  
    CloudWatch with EC2 monitors events every 5 minutes by default. You can change the monitoring time interval as per the requirement. Used for performance monitoring. CloudWatch can monitor most of AWS Services as well as the applications that run on AWS.

20. Question: How to create CloudWatch alarm? What are data points? What are metric alarms? What are composite alarms?  
    Define it in CloudWatch. Metric alarm watches a single CloutWatch metric or result of math expression based on CloudWatch metrics. Alarm performs one or more actions. Ec2 action, auto scaling, SNS.
    Composite alarm includes a rule expression that takes into account the alarm states of other alarms that you have created. Can reduce alarm noise. Can only send SNS notifications.

21. Question: How to create EC2 backup & restore?  
    1. Create snapshot of volumes. 
            2. Detach and delete corrupted volume.
            3. Create volume from snapshots.

22. Question: What is EC2 Instance Metadata?  
    It is the data that you can use to configure or manage the instances. IPv4, IPv6, Hostname, Local IP, Public IP, instance Id, keys, security groups. Basically description...

23. Question: How to get EC2 Instance Metadata?  
    1. SSH into your instance
            2. Run command `http://169.254.169.254/latest/meta-data/`
            3. You can also run commands to retrieve only 1 value: http://169.254.169.254/latest/meta-data/public-ipv4

24. Question: What is EC2 Instance User Data?  
    User Data is data supplied to user when launching instance in the form of a script. It is post installation of that instance. Example: install additional packages. Max size 16kb, not encrypted so do not store sensitive data. It is available in advanced details.

25. Question: Explain thouroughly different types of EC2 instances (spot etc.)  
    Not yet complete.

IAM

1. Question: What is IAM?  
    IAM is a web service that helps you securely control access to AWS resources. IAM controls authentication and authorization.
           It allows you to manage users and their level of access to AWS.
           It is used to set users, permissions and roles, groups etc.

2. Question: What are features of IAM?  
    Centralized control of your AWS Account, Shared Access to your Account, granular access, identity federation, mfa

3. Question: How does EC2 role work?  
    Not yet complete.

4. Question: Exam tips.  
    IAM is global. Root account is first account which has full access. New users have no permissions when first created. It is recommended to setup MFA on root account. You can customize your own password rotation policies.


S3

1. Question: What is S3?  
    AWS storage for the internet. Safe place to store files. Object based storage. 

2. Question: What are size limts on S3?  
    Files can be from 0 bytes to 5 TB with unlimited storage.

3. Question: Where are files stored?  
    In buckets which have unique names globally. AWS console is global.

4. Question: Difference between S3 vs EBS?  
4. Question: EBS = block storage. S3 = object storage. For very fast read / write then block storage is best. If your files are mostly read then object storage is preferable.  
             S3 = WORK operations (Write Once Read many times), you need to dump data, rare write operations, not suitable for OS or Database.
             EBS = server disks, persistent and high performance in terms of read and write

5. Question: Security and encryption?  
    By default all buckets are private. You can control access using bucket policies and access control lists.
           Can enable access logs to requests for s3 bucket.

6. Question: encryption?  
    SSE => S3 manager keys (SSE-S3)
               => AWS Key Management Service, Manageed Key (SSE-KMS)
               => With Customer provided keys (SSE-C)
           CSE => 

7. Recheck all things regarding cloudfront as I forgot to save file when editing cloudfront.

ROUTE 53

1. What is DNS?
    Internet service that converts domain names into their corresponding IP Addressed and vice versa.

2. What is /etc/hosts?
    It is manual local DNS for computer where you specifiy domain name to IP address.

3. What is purpose of DNS?
    DNS has been implemented to deal with task of translating domain name of any computer to its IP address.

4. Check on Internet what is DNS and its purpose and how it works.

5. What is TLD and SLD?
    Top Level Domain and Second Level Domain.

6. What are TLD's split into?
    gTLD and ccTLD

7. What are gTLD's?
   Generic top level domains, such as .com, .net, .org etc. 

8. What are ccTLD's?
    Country Code top level domains such as .si, .us, .uk etc.

9. What combination are www.example.com and google.com?
    .com => top level domain, google => secondary level domain

10. Explain how does DNS work for user going to webpage through browser.
    1. You type example.com in browser.
    2. Internal DNS Server
    3. Root-Level domain servers
    4. Top-Level domain servers (.com)
    5. Second-Level domain servers  (example)
    6. 5 reply to 2, 2 reply to 1.

11. Write example for www.example.com in browser.
    
12. What are root servers?

13. What is ROUTE 53?
    DNS (Domain Name System) that translated human readable domain name such as amazon.com into machine readable IP address such as 50.52.212.90. Route 53 Connects request of users to the system running in AWS. The system includes amazon EC2 instances, ELB, S3 buckets etc. Is compatible with IPv6

14. Example of using ROUTE 53?
    You have registered domain. You have ec2-instance and want it to be accessible from your domain.

15. Explain the following concepts: A, AAAA, ALIAS, CNAME, NS, SRV, TXT, URL redirect unamsked forwarding, URL redirect masked forwarding, URL redirect 301, MX, MXE, CAA
    A: (Address Record) associate domain name or subdomain with an ip address
    AAAA: Same as A except using IPv6.
    ALIAS: point one domain to another one, almost same as CNAME. Difference is ALIAS can coexist with other records on that name. You can alias root domain to another service.
    CNAME: domain name => domain name
    NS: subdomain => nameserver not associated with domain itself
    URL redirect: redirect a domain to another URL/domain name
    URL frame: same as redirect except instead of redirect it is displayed as frame

16. What are health checks?
    What can You do with health checks? How to make a health check?

17. List Routing Policies.
    1. Simple Routing Policy
        Use for a single resource that performs a given function for your domain.
        Example: webserver that server content for example.com website.
        You can only have on record with multiple IP Addresses.
        With multiple IP address when client makes DNS request all IP addresses are returned.
        Which IP address is chosen is random.
        Benefit is "load balancing".
        If one IP fails it will use different IP etc. No downtime.
        If client is unhealthy user experiences downtime.
        You can't add health check to simple policy.
    2. Weighted Routing Policy
        Route traffic to multiple resources in proportions that you specify.
    3. Latency-based Routing Policy
        Route traffic based on lowest network latency for your end.
        The region which will give them lowest response time.
    4. Failover Routing Policy
        Route traffic to a resource when the resource is healthy or to a different resource when the first resource is unhealthy.
    5. Geolocation Routing Policy
        If you have servers in multiple geolocations than this routing policy will route to nearest.
        Example you have 2 servers, london, mumbai. 2 Users from london and mumbai.
        Mumbai users will be routed to mumbai server, london to london server.
        You create two records set, one for each server in Route 53 with Geolocation policy.
    6. Geoproximity Routing Policy
    7. Multivalue Answer Routing Policy

18. Do example of simple routing policy with 2 servers.