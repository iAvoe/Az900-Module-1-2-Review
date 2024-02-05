# Az900-Module-1-3-Review

## Cloud Basics

### Cloud computing
- Delivery of computing services over internet
- Enabling faster innovation, flexible resources, and economies of scale

### Cloud comparison
- #### Public Cloud
  - Owned by cloud services provider or anyone that is hosting it
  - Provide resources & services to multiple organizations & users
  - Accessed Via Secure network connection (typically over internet)
  - No capital expenditures to scale up
  - Applications can be quickly provisioned and deprovisioned
  - Organizations pay only for what they use
- #### Private Cloud
  - Hardware must be purchased for start-up and maintenance
  - Organizations have complete control on resources and security
  - Organizations are responsible for hardware maintenance and updates
  - Organizations create a cloud environment in their datacenter
  - Often only provide access to internal users
- #### Hybrid Cloud
  - Most flexible
  - Organizations determine where to run their applications
  - Organizations control security, compliance, or legal requirements

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

### Infrastructure as a Service (IaaS)
A pay-as-you-go IT infrastructure - renting servers, VMs, networks

### Platform as a Service (PaaS)
An environment for developing, testing, deploying software without focusing on managing underlying infrastructure

### Software as a Service (SaaS)
Users connect to & use cloud-based apps over the internet
for example, draw.io, emails.

### Cloud service in XaaS models
- *IaaS:* The most flexible service, buyer configure & manage hardware
  - Best for website / platform providers
- *PaaS:* Targeting ease of app development, platform is handled by cloud provider
  - Best for developers
- *SaaS:* Pay-as-you-go pricing where user subscribes for the software / account
  - Best for Microsoft365, business software users

### Horizontal Scaling
- Adding more VMs or physical machines, controlled by virtual machine scale sets in Azure

### Vertical Scaling
- Upgrading the current machine, mainly CPU, RAM, storage

### List-&-shift in Cloud Migration
- Apps, Systems, Workloads, Data moved from premises to cloud with little changes
- In best case senario, it's Copy & Paste

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

<br>

## Azure Compute Services

### List of Azure Compute Services:
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

### Azure Networking Services
- **Azure Virtual Network (VNet)**
  - Allow Azure resources to intercommunicate
- **VPN Gateway**
  - Encrypt traffic between Azure VNet & an on-premises location
- **Azure Express Route**
  - Extends on-premises networks into Azure over a private connection
- **Container storage (blob):**
  - Optimized for storing large amounts of unstructured data
- **Disk Storage**
- **Azure Files**
  - Sets up a highly available network file share
  - Using Server Message Block (SMB) protocol

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

### Azure DB Services
- **Azure Cosmos DB**
  - A globally distributed DB service for high elasticity
- **Azure SQL DB**
  - A globally distributed DB service for high elasticity
- **Azure DB for MySQL**
  - A relational MSSQL DB as a service (DaaS)
- **Azure DB for PostgreSQL**
  - A relational DB service based on Postgres Engine

### Azure SQL Managed Instance
- Allows SQL-Server customers to lift-&-shift their Apps
- Has all PaaS's automatic capabilities:
  - patching, version updates, backups, high availability
- PLus **Azure Hybrid Benefit:**
  - Exchange existing licenses for discounted rates

### Azure Marketplace
- Allow customers to find, try, purchase, provision apps & services (SaaS)
  - Open-Source platforms, VMs, DB images, App builds, dev tools

### VM Scale Sets
- Create & manage a group of identical, load-balanced VMs

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






<br>

## Az900 Module 1-2 Quiz:

