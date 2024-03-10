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
- **Examples:** *Same examples as IaaS*
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
  - Allow Azure resources to intercommunicate
  - Virtual network peering can be used to allow 2 virtual networks to communicate
- **Azure Express Route**
  - Extends on-premises networks into Azure over a private fibre connection
  - Convert private cloud to hybrid cloud
  - Support for bandwidth up to 100 Gbps
- **VPN Gateway**
  - Alternate option than building a private fibre connection
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

#### Which of the following statement is valid about an Azure subscription?
- An Azure subscription is a logical unit of Azure services

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

#### Which type of scaling involves adding or removing resources (such as virtual machines or containers) to meet demand?
- Horizontal scaling (Adding nodes, without upgrading current machine)

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

-----

### ExpressRoute & VPN

#### Tailwind Traders wants to create a secure communication tunnel between its branch offices. Which of the following technologies can't be used?
- Implicit FTP over SSL

#### Which of the following options isn't a benefit of ExpressRoute?
- Encrypted network communication

#### ________ is supported by ExpressRoute for connecting an on-premises network to Azure
- A point-to-point Ethernet connection

#### How many VPN gateways can you deploy in each virtual network?
- 1: VPN gateway OR ExpressRoute gateway

#### Tailwind Traders wants to use Azure ExpressRoute to connect its on-premises network to the Microsoft cloud. Which of the following choices isn't an ExpressRoute model that Tailwind Traders can use?
- Site-to-site virtual private network (VPN)

#### Which option is used to set the communication between an on-premises VPN device and an Azure VPN gateway through an encrypted tunnel over the internet?
- Site-to-Site VPN

-----

### Billing

#### Which of the following statements is true?
- With Operating Expenses (OpEx), you are only responsible for the computing resources that you use

#### ________ estimates workload costs
- Pricing calculator

#### ________ estimates the cost savings by comparing datacenter costs to running the same workload on Azure
- TCO calculator

#### What's the best method to estimate the cost of migrating to the cloud while incurring minimal costs?
- Use the Total Cost of Ownership calculator to estimate expected costs

#### ________ helps control, analyze, and optimize workload costs
- Cost management

#### You plan to build a new solution in Azure that will use platform as a service (PaaS) products. What should you use to estimate the monthly costs?
- Azure Pricing calculator

#### What is the main difference inbetween Total Cost of Ownership (TCO) and Azure Pricing calculator?
- TCO calculator estimates the cost of running an environment in Azure
- Azure Pricing Calculator checks the cost of modifying plans and service grades in Azure

#### Which of the following sentences best describes platform as a service (PaaS)?
- Users can create & deploy an application as quickly as possible without having to worry about managing the underlying infrastructure.

#### For which resource does Azure generate separate billing reports and invoices by default?
- Azure Subscriptions

-----

### IaaS, PaaS, SaaS

#### In a platform as a service (PaaS) model, which two components are the responsibility of the cloud service provider?
- Operating System & Physical Network

#### What type of cloud service type would a Finance and Expense tracking solution typically be in?
- SaaS

#### Which type of cloud service model is typically licensed through a monthly or annual subscription?
- SaaS

#### In which cloud service model is the customer responsible for managing the operating system?
- SaaS

#### Which type of cloud service are virtual networks?
- IaaS

#### Which of the following requires the most user management of cloud services?
- IaaS

#### Which cloud service type is most suited to a lift-&-shift migration from an on-premises data center to a cloud deployment?
- IaaS

####  According to the shared responsibility model, in which service model is the cloud provider only responsible for the basics of physical security, power, and connectivity.
- IaaS

#### ________ provides hosting and management of an application and its underlying infrastructure, as well as any maintenance, upgrades, and security patching
- Software as a service (SaaS)

#### ________ provides a fully managed environment for developing, testing, delivering, and managing cloud-based applications
- Platform as a service (PaaS)

#### ________ provides servers and virtual machines, storage, networks, and operating systems on a pay-as-you-go basis
- Infrastructure as a service (IaaS)

#### Which of the following choices isn't a cloud computing category?
- Network-as-a-Service (NaaS)

-----

### High Availability & Compliance boundaries

#### Which of the following terms relates to making a service available with no downtime for an extended period?
- High availability

#### Which storage redundancy option provides the highest degree of durability, with 16 nines of durability?
- Geo-Redundant storage (GRS)

#### ________ copies data to a secondary region from the primary region across multiple datacenters that are located many miles apart.
- Geo-redundant storage (GRS)

#### Which Azure Virtual Machine feature staggers updates across VMs based on their update domain and fault domain?
- Availability sets
- Note: Stagger means random-sequentially

#### Rank Azure Architectual Components by their distance apart
- Regions < Availability Zones < Region Pairs < Geographies

#### What Azure feature replicates resources across regions that are at least 300 miles away from each other?
- Region Pairs

#### ________ in Azure enables you to deploy Azure resources close to the users.
- Geo-distribution

#### In cloud computing, ________ allows you to deploy applications to regional datacenters around the world.
- Geo-location / get-distribution

#### What is high availability in a public cloud environment dependent on?
- The service-level agreement (SLA) that you choose

### Resource & Management Groups

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

#### Which Azure feature enables you to organize multiple subscriptions in hierarchies for unified policies and compliance?
- Management groups

#### Which of the following can be used to manage governance across multiple Azure subscriptions?
- Management groups

#### Which resource can you use to manage access, policies, and compliance across multiple subscriptions?
- Management groups

-----

### Scalability and elasiticy

#### What is horizontal scaling
- Adding more computing nodes (PCs or VMs)

#### Which Azure compute resource can be deployed to manage a set of identical virtual machines?
- Virtual machine scale sets

#### ________ enables you to provision a group of matching and load-balanced virtual machines in Azure.
- An Azure virtual machine scale set

#### ________ enables you to scale to thousands of virtual machines for high-performance computing and large-scale parallel jobs.
- Azure Batch

-----

### Security features

#### Which Azure Active Directory tool can vary the credentials needed to log in based on signals, such as where the user is located?
- Conditional Access

#### Which Azure Active Directory (Azure AD) feature is used to provide access to resources based on organizational policies?
- Conditional Access

#### Which security model assumes the worst-case security scenario, and protects resources accordingly?
- Zero trust

#### What can you use to restrict the deployment of a virtual machine to a specific location?
- Azure Policy

#### What can you use to ensure that a development team can only create virtual machines of a certain size?
- Azure Policy

#### ________ enforces standards and assess compliance across your organization
- Azure Policy

#### You need to recommend a solution for Azure virtual machine deployments. The solution must enforce company standards on the virtual machines. What should you include in the recommendation?
- Azure Policy

#### How can you prevent non-compliant resources from being created, without having to manually evaluate each resource as it's created?
- Azure Policy

#### ________ is a repeatable set of governance tools that helps development teams quickly build and create new environments while adhering to organizational compliance to speed up development and deployment.
- Azure Policy

#### You need to ensure that multi-factor authentication (MFA) is enabled on accounts with write permissions in an Azure subscription. What should you implement?
- Azure Policy

#### You receive an email notification that virtual machines (VMs) in an Azure region where you have VMs deployed is experiencing an outage. Which component of Azure Service Health will let you know if your application is impacted?
- Resource health

#### Which defense in depth layer uses distributed denial of service (DDoS) protection?
- Perimeter layer

-----

### Unsorted

#### Which of the following options can you use to link virtual networks?
- Multi-chassis link aggregation (MC-LAG)

#### Which tool automatically keeps files between an on-premises Windows server and an Azure cloud environment updated?
- Azure File Sync




