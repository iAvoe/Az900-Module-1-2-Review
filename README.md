# Az900-Module-1-2-Review

## Cloud Basics

### Cloud computing
- Delivery of computing services over internet
- Enabling faster innovation, flexible resources, and economies of scale

### Cloud comparison
- #### Public Cloud
  - Owned by cloud services provider or anyone that is hosting it
  - Provide resources & services to multiple organizations & users
  - Accessed Via Secure network connection (typically over internet)
  - Scale up by OpEx (operational expenditure)
  - Applications can be quickly provisioned and deprovisioned
  - Organizations pay only for what they use
- #### Private Cloud
  - Hardware must be purchased for start-up and maintenance
  - Scale up by CapEx (capital expenditure)
  - Organizations have complete control on resources and security
  - Organizations are responsible for hardware maintenance and updates
  - Organizations create a cloud environment in their datacenter
  - Often only provide access to internal users
- #### Hybrid Cloud
  - Most flexible
  - Organizations determine where to run their applications
  - Organizations control security, compliance, or legal requirements

-----

### Capital Expenditure (CapEx / buy)
- The up-front spending of money on physical infrastructure, investment-like
- Like investment, depreciates over time

### Operational Expenditure (OpEx / rent)
- Spend on products and services as needed, pay-as-you-go, rental
- Upscale & downscale on-demand
- Easier to predict cost

### Consumption-based model / rental
- Easier to predict cost
- Only pay for the resources needed
- Prices for individual resources and services are provided
- Billing is based on actual usage

-----

### On-premise DIY:
- Private cloud, or not a cloud at all

### Infrastructure as a Service (IaaS)
- A pay-as-you-go IT infrastructure - renting servers, VMs, networks
- **Examples:** IBM Cloud, Amazon AWS, MS Azure, Alibaba Cloud
- **Benefits:**
  - Buyer configure & manage hardware
  - More configurable (flexible) than PaaS, SaaS
  - Can be more cost-effective than on-premise DIY
- **Tgt. use:** Large website platform backend; compute farms; hybrid cloud that require exact same hardware, same driver / firmware

### Platform as a Service (PaaS)
- An environment for developing, testing, deploying software without focusing on managing the underlying infrastructure
- **Examples:** *Same examples as IaaS*, Azure SQL Database
- **Benefits:**
  - Skip (some of) the environment setup procedures and get to development
  - Can be more cost-effective than on-premise DIY
  - Can be very time-effective than on-premise DIY
- **Tgt. use:** Small-medium website platform backend and front end, render farms
- **Note:** Usually mixed with IaaS service by cloud providers

### Software as a Service (SaaS)
- Users connect to & use cloud-based apps over the internet
- **Examples:** Microsoft365, draw.io, Emails, Google drive, business software, MSSQL Database users
- **Benefits:** Pay-as-you-go pricing where user subscribes for the software / account
- **Tgt. use:** front-end (client-side) service

-----

### Horizontal Scaling
- Adding more VMs or physical machines, controlled by virtual machine scale sets in Azure

### Vertical Scaling
- Upgrading the current machine, mainly CPU, RAM, storage

### List-&-shift in Cloud Migration
- Apps, Systems, Workloads, Data moved from premises to cloud with little changes
- In best case senario, it's Copy & Paste

### Elasticity
- How fast (defined) should/could horizontal scaling take action

### Agility
- How fast could an user / organization quickly and easily deploy cloud service
- Related to lift-&-shift approach

### Disaster Recovery
- How fast could disaster recovery be completed
- How identical could the recovered service be, compared to the killed service

-----

<br>

## Azure Architectual Components

### Rank Azure Architectual Components
- Fault Domain `<` Availability Set `<` Data Center `<` Availability Zone `<` Region `<` Region Pairs `<` Geographies

### Regions
- One or many availability zones in close proximity
- Reduce customer latency by having service a close-by infrastructure

### Availability zones
- Datacenters with dedicated power, cooling, networking
- Connected through private fiber-optic networks within a region
- Protection against downtime, but not as expensive as region pairs

### DC (datacenter) Region Pairs
- At least 300 miles of datacenter separation in case of regional disaster
- Prioritized region recovery in the event of outage
- Rollout updates sequentially to minimize downtime
- Auto-replication for some services

### Geographies (Countries)
- Preserve data residency - localized content & ads
- Follow compliance boundaries - some data has to be stored within a region
- Typically contain two or more regions:
  - Americas, Europe, Asia Pacific, Middle East, Africa

-----

### Azure Resources
- AppSvcs, Virtual Nets, Storage Accounts, VMs, DBs, Functions

### Resource groups
- Logically bounds computing, storage, scaling, networking resources in a group
- A resouce group is under an Azure account
- *Merged group:* Web + Database, VM, Storage in one group
- *Co-exist group:* Web+ Database group, VM group, Storage group

### Azure Subscriptions
- *Billing boundary:* How an Azure account will be billed, generated for each sub
- *Access control boundary:* (Policies) How end users (in each business department & public users) have access for each sub

### Azure Resource Manager (ARM)
- A management layer to create, update, delete resources
- The backbone of Azure itself
- Usable under each Azure subscription

### Management Groups
- Include multiple Azure subs, each sub can inherit mgmt. group's conditions 
- 10,000 management groups can be supported in a single directory
- Support up to 6 levels of depth:
  - subscriptions → resource groups → resources

-----

<br>

## Azure Compute Services

### Compute Services:
- **App Service**
  - A fully managed platform to build, deploy, scale web apps/APIs
- **VMs**
  - Emulation of physical computers
- **Azure Virtual Desktop**
  - Desktop & app virtualization in the cloud
  - Allows multifactor authentication to secure user sign-in
  - Allows better data security because data is not on worker's laptop
  - Allows multi-user to be inside a single Windows10/11 VM
- **Container Instances**
  - A PaaS offering that runs a container in Azure
- **Azure Kubernetes Services (AKS)**
  - An orchestration service for:
  - Containers with distributed architectures
  - Large volumes of containers

### Networking Services
- **Azure Virtual Network (VNet)**
  - Networks in Azure between VMs are known as virtual networks.
  - A virtual network can have multiple IP address spaces and multiple subnets
  - Azure automatically routes traffic between different subnets within a virtual network.
- **Azure Virtual Network Service Endpoints**
  - Connect Azure resources to an Azure virtual network
- **Azure Express Route**
  - Extends on-premises networks into Azure over a private fibre connection
    - Site to VNet
  - Convert private cloud to hybrid cloud
  - Support for bandwidth up to 100 Gbps
- **VPN Gateway**
  - Alternate option than building a private fibre connection
    - Site to VNet
  - Encrypt traffic between Azure VNet & an on-premises location
  - Supports site-to-site VPN, and point-to-site VPN
- **Container storage (blob):**
  - Optimized for storing large amounts of unstructured data
  - Can contain thousands of files containing text and images
- **Disk Storage**
- **Azure Files**
  - Sets up a highly available network file share
  - Using Server Message Block (SMB) protocol

### DB Services
- **Azure Cosmos DB**
  - A globally distributed DB service for high elasticity
- **Azure SQL DB**
  - A globally distributed DB service for high elasticity
- **Azure DB for MySQL**
  - A relational MSSQL DB as a service (DaaS)
- **Azure DB for PostgreSQL**
  - A relational DB service based on Postgres Engine

-----

### Storage access tiers
- **Hot**
  - Data/Disk that is accessed frequently
- **Cool**
  - Data/Disk that is accessed infrequently
  - & stored for at least 30 days
- **Archive**
  - Data/Disk that is accessed rarely
  - & stored for at least 180 days
  - & latency is not a problem

-----

### Azure SQL Managed Instance
- Allows SQL-Server customers to lift-&-shift their Apps
- Has all PaaS's automatic capabilities:
  - patching, version updates, backups, high availability
- PLus **Azure Hybrid Benefit:**
  - Exchange existing licenses for discounted rates

### Azure Marketplace
- Allow customers to find, try, purchase, provision apps & services (SaaS)
  - Open-Source platforms, VMs, DB images, App builds, dev tools

-----

### VM Scale Sets
- Create & manage a group of identical, load-balanced VMs
- Lab: Create a Virtual Machine Scale set:
  - Configure number of minimum & maximum instances
  - scale-out duration & CPU threshold(%)
  - scale-in duration, CPU threshold & decrease-by count

### VM Availability Sets
- **Update Domain:**
  - Groups VMs that can be rebooted at the same time
  - Only one update domain grouping will be offline at a time
  - All machines in an update domain will be updated
  - An update group going through the update process is given a 30min time to recover before maintenance on the next update domain starts
- **Fault Domain:**
  - Groups VMs by common power source & network switch
  - By default, an availability set will split your VMs across up to 3 fault domains
  - Helps protect against a power or networking failure

-----

<br>

## Az900 Module 1-2 Quiz:


## AAA (Authentication Authorization and Accounting)

#### Which of the following is a logical unit of Azure services that links to an Azure account?
- Azure subscription

#### A user is simultaneously assigned multiple roles that use role-based access control. What are their actual permissions? The role permissions are:
#### Role 1 - read || Role 2 - write || Role 3 - read and write.
- Read and write

#### ________ prevents resources from being accidentally deleted or changed
- Azure Resource Locks

#### ________ confirms the identity of a person who wants access
- Authentication

#### ________ grants the proper access to a legitimate user
- Authorization

#### Single sign-on (SSO) is an ________ method that enables users to sign in the first time and access various applications and resource by using same password.
- Authentication

#### A user has logged in his/her account, then performed a Captcha to verify that he/she is not a robot, he/she has performed an ________ and an ________.
- Authentication, Authentication

-----

### Storage

#### What is a blob?
- Binary large objects (e.g., thousands of files containing text, images image and video)

#### Which Azure Storage option is better for storing data for backup and restore, disaster recovery, and archiving?
- Azure Blob Storage

#### Which Azure Storage service supports big data analytics, as well as handling text and binary data types?
- Azure Blobs

#### Which Azure Storage service should you use to store unstructured files, such as images, that will be served on webpages?
- Azure Blobs

#### What is the first step that you would take in order to share an image file as a blob in Azure Storage?
- Create an Azure Storage account

#### Which Azure Blob storage tier Stores data offline, Offers the lowest storage costs, and has the highest costs to access data?
- Archive tier

#### Which Azure Blob storage service tier has the highest storage costs and the fastest access times for reading and writing data?
- Hot tier

#### Which two scenarios are common use cases for Azure Blob storage?
- Serving images or documents directly to a browser
- Storing data for backup and restore 

#### You need to purchase an Azure account before you can use any Azure resources
- False

#### Which storage service offers fully managed file shares in the cloud that are accessible by using Server Message Block (SMB) protocol?
- Azure Files

#### Which two protocols can be used to access Azure file shares? 
- Server Msssage Block (SMB)
- Network File System (NFS)

-----

### Cloud definition

#### Which best describes cloud computing?
- Delivery of computing services over the internet

#### Which of the following is not a feature available in Cloud computing?
- A limited pool of services

#### Which cloud model uses some data centers focused on providing cloud services to anyone that wants them, and some on-premises data centers that are focused on a single customer?
- Hybrid Cloud

#### Which cloud approach is used by organizations to take full advantage of on-premises technology investments and allows data and applications to be shared between two environments?
- Hybrid cloud

-----

### Cloud benefits

#### What is characterized as the ability of a system to recover from failures and continue to function?
- Resiliency

#### Which of the following choices isn't a benefit of using cloud services?
- Geographic isolation

#### Which of the following options isn't a type of cloud computing?
- Distributed cloud

#### Your company has a team of remote workers that need to use Windows-based software to develop your company's applications, but your team members are using various operating systems like macOS, Linux, and Windows. Which Azure compute service would help resolve this scenario?
- Azure Virtual Desktop

#### Which Azure service allows users to use a cloud-hosted version of Windows from any location and connect from most modern browsers?
- Azure Virtual Desktop

#### What can you use to provide Mac and Android users with access to a Windows environment that will run Windows-based applications?
- Azure Virtual Desktop

-----

### Azure Networking Services

#### Which tool automatically keeps files between an on-premises Windows server and an Azure cloud environment updated?
- Azure File Sync

#### Tailwind Traders wants to create a secure communication tunnel between its branch offices. Which of the following technologies can't be used?
- Implicit FTP over SSL

#### Which of the following options isn't a benefit of ExpressRoute?
- Encrypted network communication

#### ________ is supported by ExpressRoute for connecting an on-premises network to Azure
- A point-to-point Ethernet connection

-----

### Virtual Private Network (VPN) Gateway

#### How many VPN gateways can you deploy in each virtual network?
- 1 gateway: VPN gateway OR ExpressRoute gateway
- Note: Site to VNet

#### Tailwind Traders wants to use Azure ExpressRoute to connect its on-premises network to the Microsoft cloud. Which of the following choices isn't an ExpressRoute model that Tailwind Traders can use?
- Site-to-site virtual private network (VPN)

#### Which two services can you use to establish network connectivity between an on-premises network and Azure resources?
- Azure VPN Gateway
- ExpressRoute
- Note: Site to VNet

#### Which option is used to set the communication between an on-premises VPN device and an Azure VPN gateway through an encrypted tunnel over the internet?
- Site-to-Site VPN

#### Which scenario is a use case for a VPN gateway?
- Connecting an on-premises datacenter to an Azure virtual network
- Note: Site to VNet

-----

### Virtual Network / VNet

#### You need to allow resources on two different Azure virtual networks to communicate with each other. What should you configure?
- Virtual Network peering / VNet Peering
- Note: VNet to VNet

#### What can you use to connect Azure resources, such as Azure SQL databases, to an Azure virtual network?
- Service Endpoints
- Note: Resource to VNet & Service to VNet

#### Your company has virtual machines (VMs) hosted in Microsoft Azure. The VMs are located in a single Azure virtual network named VNet1.
#### The company has users that work remotely. The remote workers require access to the VMs on VNet1. To provide access for the remote workers, you:
- Configure a Point-to-Site (P2S) VPN
- Note: Point to Site, then Site to VNet

#### Which of the following options can you use to link virtual networks?
- Multi-chassis link aggregation (MC-LAG)
- Note: VNet to VNet

#### Your company plans to move several servers to Azure. The company's compliance policy states that a server named FinServer must be on a separate network segment. Which Azure solution should you recommend?
- A virtual network for FinServer and another virtual network for all the other servers
- Note: separation means creating subnet or VLANs, which in Azure is to create a VNet

#### You have an Azure environment that contains multiple Azure virtual machines. You plan to implement a solution that enables the client computers on your on-premises network to communicate to the Azure virtual machines. You need to recommend which Azure resources must be created for the planned solution. What 2 Azure resources should you include in the recommendation?
- A virtual network gateway
- A gateway subnet
- Note: Site to VNet

-----

### Resource & Management Groups

#### What is an Azure Storage account named storage001 an example of?
- A resource

#### What happens to the resources within a resource group when an action or setting at the Resource Group level is applied?
- The setting is applied to current and future resources

#### Which of the following features does not apply to resource groups?
- Resource groups can be nested

#### How many resource groups can a resource be in at the same time?
- One

#### You use _________ to organize resources in an Azure subscription.
- Resource groups

#### __________ is the logical container used to combine and organize Azure resources.
- Resource groups

#### You use __________ to organize resources in an Azure subscription.
- Resource groups

#### Which Azure feature enables you to organize multiple subscriptions in hierarchies for unified policies and compliance?
- Management groups

#### Which of the following can be used to manage governance across multiple Azure subscriptions?
- Management groups

#### Which resource can you use to manage access, policies, and compliance across multiple subscriptions?
- Management groups

-----

### Azure Subscription

#### Which 2 components can be created by an Azure subscription?
- Azure Account
- Azure Resource

#### Which of the following statement is valid about an Azure subscription?
- An Azure subscription is a logical unit of Azure services

#### Your company plans to migrate all its network resources to Azure. You need to start the planning process by exploring Azure. What should you create first?
- Subscription

#### For which resource does Azure generate separate billing reports and invoices by default?
- Azure Subscriptions

-----

### Billing

#### ______ refers to upfront costs incurred one time, such as hardware purchases.
- Capital expenditure (CapEx)

#### Which of the following statements is true?
- With OpEx, you are only responsible for the computing resources that you use

#### Why is cloud computing often less expensive than on-premises datacenters?
- You are only billed for what you use

#### Which two factors affect Azure costs?
- Resource Location (Different regions have different operating costs in electricity, cooling)
- Resource Usage (CPU, Disk size, Disk type)

#### What is the difference inbetween Pricing calculator and TCO calculator?
- Pricing calculator provides an estimate of the cost of Azure products and services
- Pricing calculator is for monthly PaaS
- TCO calculator helps you assess the potential financial impact of deploying Azure
- TCO calculator is made for IaaS

#### You plan to build a new solution in Azure that will use PaaS products. What should you use to estimate the monthly costs?
- Azure Pricing calculator

#### ________ estimates workload costs
- Azure Pricing calculator

#### You need to compare the costs of running an application in an on-premises datacenter with the costs of running the application in Azure. What should you use to assist you?
- Total Cost of Ownership (TCO) Calculator

#### ________ estimates the cost savings by comparing datacenter costs to running the same workload on Azure
- Total Cost of Ownership (TCO) calculator

#### What's the best method to estimate the cost of migrating to the cloud while incurring minimal costs?
- Use the Total Cost of Ownership (TCO) calculator to estimate expected costs

#### What is the main difference inbetween Total Cost of Ownership (TCO) and Azure Pricing calculator?
- TCO calculator estimates the cost of running an environment in Azure
- Azure Pricing Calculator checks the cost of modifying plans and service grades in Azure

#### ________ helps control, analyze, and optimize workload costs
- Cost management

#### Which two features are available by using Azure Cost Management + Billing?
- Create and manage budgets
- Generate historical reports and forecast future usage

-----

### IaaS, PaaS, SaaS

#### What uses the IaaS cloud service model?
- Azure virtual machines

#### Which of the following sentences best describes PaaS?
- Users can create & deploy an application as quickly as possible without having to worry about managing the underlying infrastructure.

#### What is the customer responsible for in a SaaS model?
- Data and access

#### In a PaaS model, which two components are the responsibility of the cloud service provider?
- Operating System
- Physical Network

#### ________ provides hosting and management of an application and its underlying infrastructure, as well as any maintenance, upgrades, and security patching
- SaaS

#### Which cloud service model is used by Microsoft Office 365?
- SaaS

#### What type of cloud service type would a Finance and Expense tracking solution typically be in?
- SaaS

#### Which type of cloud service model is typically licensed through a monthly or annual subscription?
- SaaS

#### Your organization is building a custom application. You need to focus on application development rather than configuration and management of servers. Which cloud service model should you use?
- PaaS (You don't know what software and tools the devs really use)

#### ________ provides a fully managed environment for developing, testing, delivering, and managing cloud-based applications
- PaaS

#### Which cloud service model is used by Azure SQL Database?
- PaaS

##### In which two deployment models are customers responsible for managing operating systems that host applications?
- IaaS
- on-premises

#### In which cloud service model is the customer responsible for managing the operating system?
- IaaS

#### Which of the following requires the most user management of cloud services?
- IaaS

#### Which cloud service type is most suited to a lift-&-shift migration from an on-premises data center to a cloud deployment?
- IaaS

####  According to the shared responsibility model, in which service model is the cloud provider only responsible for the basics of physical security, power, and connectivity.
- IaaS

#### Which type of cloud service are virtual networks?
- IaaS

#### ________ provides servers and virtual machines, storage, networks, and operating systems on a pay-as-you-go basis
- IaaS

#### Which of the following choices isn't a cloud computing category?
- Network-as-a-Service (NaaS)

-----

### High Availability & Compliance boundaries

#### What are cloud-based backup services, data replication, and geo-distribution features of?
- A disaster recovery plan

#### Which of the following terms relates to making a service available with no downtime for an extended period?
- High availability

#### Which Azure Virtual Machine feature staggers updates across VMs based on their update domain and fault domain?
- Availability sets
- Note: Stagger means random-sequentially

#### What is high availability in a public cloud environment dependent on?
- The service-level agreement (SLA) that you choose

#### In a region pair, a region is paired with another region in the same
- Geography

#### What is the physical infrastructure that a region pair resides in?
- Geographies

#### What Azure feature replicates resources across regions that are at least 300 miles away from each other?
- Region Pairs

#### Which Azure component allows you to replicate resources across a geography to ensure business continuity during a natural disaster at the primary site?
- Region Pairs

#### ________ in Azure enables you to deploy Azure resources close to the users.
- Geo-distribution

#### In cloud computing, ________ allows you to deploy applications to regional datacenters around the world.
- Geo-location / get-distribution

#### Which two Azure resources can make use of availability zones?
- Azure SQL databases 
- Virtual Machines

#### Which storage redundancy option provides the highest degree of durability, with 16 nines of durability?
- Geo-Redundant storage (GRS)

#### ________ copies data to a secondary region from the primary region across multiple datacenters that are located many miles apart.
- Geo-redundant storage (GRS)

-----

### Scalability, agility and elasiticy

#### What is an advantage of cloud computing compared to on-premises deployments?
- You can scale more quickly

#### Which type of scaling involves adding or removing resources (such as virtual machines or containers) to meet demand?
- Horizontal scaling (Adding nodes, without upgrading current machine)

#### Adding more RAM and upgrading CPUs is called
- Vertical Scalling

#### Which Azure compute resource can be deployed to manage a set of identical virtual machines?
- Virtual machine scale sets

#### ________ enables you to provision a group of matching and load-balanced virtual machines in Azure.
- An Azure virtual machine scale set

#### ________ enables you to scale to thousands of virtual machines for high-performance computing and large-scale parallel jobs.
- Azure Batch

#### You have an Azure virtual machine that is accessed only between 9:00 and 17:00 each day.  What should you do to minimize costs but preserve the associated hard disks and data?
- Deallocate the virtual machine when it is not needed

#### An example of ________ is automatically scaling an application to ensure that the application has the resources needed to meet customer demands.
- Elasiticity

#### Deploying and configuring cloud-based resources quickly as business requirements change is called?
- Agility

-----

### Security features (see M5)

-----

### Containers

#### What are two services that allow you to run applications in containers?
- Azure Kubernetes Service (AKS)
- Azure Container Instances