### Tenzar DX Pricing

DX offers a pay-as-you-go approach for pricing. With DX you pay only for your team's utilization and consumption of DX's services. DX pricing is similar to how you pay for utilities like water or electricity. You only pay for the services you consume, and once you stop using them, there are no additional costs or termination fees.


#### Pricing Architecture

The following diagram displays DX's pricing components:

[image of pricing]


#### Storage Pricing

You can store as much data as you would like in DX and you only pay for the amount of GBs your volumes and images use. Storage is prorated by the hour and billed per month.

|Storage | Per GB / month |
|--------|-------|
|For all files and folders | $ |
|For all Docker images | $ |

<br/>
Your first 1 GB of storage is always free.


#### Smart Data Throughput Pricing

Smart Data throughput is calculated as the amount of new data that you move into, out of, and through DX. There are no limits for data throughput. Smart Data throughput is calculated per GB and billed per month. Sharing and importing data with other Tenzar DX accounts does not count towards billable throughput, since it's already within Tenzar DX.

Repeated uploads or imports with the same data are automatically detected and not counted towards your Smart Data Throughput. 

|Data Throughput | Per GB|
|--------|-------|
|Unlimited data throughput | $ |

<br/>
When you create your Tenzar DX account, you get 1 GB of data throughput credit at no cost.

#### Compute Pricing

<br/>

###### Entry Instances
|Instance	| CPUs	| Memory | Price / MIN
|---------|---------|---------|---------|
|E1	| 2	| 4 GB	|0.2¢|

<br/>

###### Standard Instances

|Instance	| CPUs	| Memory | Price / MIN
|---------|---------|---------|---------|
|S1	| 4	| 16 GB	| 0.4¢
|S2	| 8	| 32 GB	| 0.7¢
|S4	| 16	| 64 GB	| 1.4¢
|S10 |	40	| 160 GB	| 3.4¢
|S16	| 64	| 256 GB	| 5.4¢

<br/>

###### Compute Instances

|Instance	| CPUs	| Memory | Price / MIN
|---------|---------|---------|---------|
|C1	|4	|7.5 GB	|0.4¢|
|C2	|8	|15 GB	|0.7¢|
|C4	|16	|30 GB|	1.4¢|
|C8	|36	|60 GB|	2.7¢|

<br/>

###### GPU Instances

|Instance	| CPUs	| Memory | GPUs| Price / MIN
|---------|---------|---------|---------|---------|
|GC1	|4	|61 GB	|1|	1.5¢|
|GC8	|32|	488 GB|	8|	12.0¢|

<br/>

###### Memory Instances

|Instance	| CPUs	| Memory | Price / MIN
|---------|---------|---------|---------|
|M1	|4	|30.5 GB	|0.5¢
|M2	|8	|61 GB	|0.9¢
|M4	|16	|122 GB	|1.8¢
|M8	|32	|244 GB	|3.6¢
|M16|	64	|488 GB	|7.1¢

<br/>

When you create your Tenzar DX account, you get 1,000 minutes of compute credit towards E1 type instances.

For example: you can use up to 1,000 minutes of compute time at no cost to run any number of E1 instances. Other instance types are not included in your free 1,000 compute minutes and are therefore billed at their current rate.

#### Computing Disk Space Pricing
Each instance includes a default 20 GB of available disk space in addition to the disk space consumed by the included data in your deployment such as your image and volume. If you plan on utilizing more than the available 20GB of free disk space in your instance, you can add up to 1 TB of extra disk space to your instance. Disk space is billed per GB per minute for the duration of your deployment.


|Disk Space | Per GB / MIN |
|----|----|
|Up to 1 TB | $ |


When you create your Tenzar DX account, you get 1,000 minutes of computing disk space credit towards E1 type instances.

#### Container Runtime Pricing

Tenzar DX automatically deploys, runs, and orchestrates your Docker containers ("environments") on top of your instances. Container runtime cost is calculated based on the amount of CPUs, Memory, and GPUs of your instance and is billed per minute for the duration your instance *running*. That is, your container runtime billing does not include the time it takes for your instance to launch and create, only from the moment is ready for use ("running") to the moment you destroy it.

###### Container Runtime
| Per CPU / MIN | Per GB Memory / MIN | Per GPU / MIN |
|-----------|-----------------|-----------|
| $ | $ | $|

<br/>

For example: running your container on an E1 instance with 2 CPUs and 4 GBs of memory, would be charged as: (2CPUs X 0.07¢) + (4GBsMemory X 0.01¢) + (0GPUs X 0.7¢) = 0.18¢ per minute for the container runtime. The cost of the instance is not included in the container runtime.


When you create your Tenzar DX account, you get 1,000 minutes of container runtime credit towards E1 type instances.

### Concurrency Pricing

Tenzar DX enables you to run up to 64 instances simultaneously across your entire team. The total number of instances that you have running at any given time is called "concurrency" -- concurrency is defined as the number of simultaneous active instances. Concurrency charges are only applicable when you have two or more instances running at the same time. Concurrency is billed as a single charge per additional concurrent deployment, and is based on the amount of additional CPUs, Memory, and GPUs of such deployment.

|Concurrency| Per Concurrent Instance |
|-----------|-----|
|1 instance running| $0|
|2 or more instances running | Concurrency fee |

<br/>


| Deployment Concurrency Fee | Per CPU | Per GB Memory | Per GPU |
|--|--|
|  | $ | $ | $  |


For example: if there is only one instance running at any given time, your concurrency is one and a concurrency fee does not apply. Say that you would now like to deploy an additional instance of type S1 *while* the initial instance is still on. In such case, your concurrency would increase to two, and a concurrency fee is applied to your second deployment. Since you deployed an S1 instance with 4 CPUs and 16 GB Memory, the concurrency fee would be calculated as: (4CPUs X $1) + (16GBs X $1) = $YYY.

Note that a concurrency fee is transactional, which means it is charged once when you launch your second instance, and it is not a per minute fee. If you need to deploy an additional instance while your two instances are running, your concurrency would increase to three and a concurrency charge would be calculated for that deployment.
