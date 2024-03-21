# TERMINOLOGY

## SOLUTIONS ARCHITECT

A role in a technical organization that architects a technical solution using multiple systems via research, documentation, and experimentation.

## CLOUD ARCHITECT

A solution architect is solely focused on architecting technical solutions using cloud services.

A cloud architect needs to understand the following terms and factor them into their designed architecture based on the business requirements.

**Availability** - Your ability to ensure a service remains available i.e. **Highly Available (HA**)
**Scalability** - Your ability to grow rapidly or unimpeded
**Elasticity** - Your ability to shrink and grow to meet the demand
**Fault Tolerance** - Your ability to shrink and grow to meet demand
**Disaster Recovery** - Your ability to recover from a failure i.e. **Highly Durable (DR)**

        A Solutions Architect needs to always consider the following business factors:
        * (Security) How secure is this solution?
        * (Cost) How much is this going to cost?

## HIGH AVAILABILITY

The ability of your service to **remain available** by ensuring there is _no single point of failure_ and/or ensure a certain level of performance.

![Screenshot 2024-03-20 at 6 11 31 PM](https://github.com/EddyKaggia/azure-fundamentals/assets/79530586/cb68261f-742d-4dc1-9e13-91e89b7ca3bc)


### Azure Load Balancer

- A load balancer allows you to evenly distribute traffic to multiple servers in one or more datacenters.
- If a datacenter or server becomes unavailable (unhealthy) the load balancer will route the traffic to only available datacenters with servers.

Running your workload across multiple **Availability Zones** ensures that 1 or 2 **AZs** become unavailable your service/ applications remain available.

## HIGH SCALABILITY

### Vertical Scaling (Scaling Up)

![Screenshot 2024-03-20 at 6 18 29 PM](https://github.com/EddyKaggia/azure-fundamentals/assets/79530586/8004484e-8320-442b-a3c4-7c0905633ce6)

Upgrade to a bigger server

### Horizontal Scaling (Scaling Out)

![Screenshot 2024-03-20 at 6 18 45 PM](https://github.com/EddyKaggia/azure-fundamentals/assets/79530586/4385586c-2f4a-4d91-9e5b-85c38d3b33ec)

Add more servers of the same size

## HIGH ELASTICITY

Your ability to **automatically** increase or decrease your capacity based on the current demand of traffic, memory, and computing power

### Horizontal Scaling

![Screenshot 2024-03-20 at 6 28 47 PM](https://github.com/EddyKaggia/azure-fundamentals/assets/79530586/e5aa6fd7-7467-4a09-8c59-f50320479c77)

> #### Azure VM Scale Sets

    Automatically increase or decrease in response to demand or a defined schedule.

> ### SQL Server Stretch Database

    Dynamically stretch warm and cold transactional data from Microsoft SQL Server 2016 to Microsoft Azure.

Scaling **Out** - Add more servers of the same size
Scaling **In** - Remove more servers of the same size

Vertical scaling is generally hard for traditional architecture so you'll usually only see horizontal scaling described with Elasticity.

## FAULT TOLERANT

The ability of your service to ensure there is _no single point of failure_. **Preventing** the chance of failure.

**Fail-overs** are when you have a plan to shift traffic to a redundant system in case the primary system fails.

![Screenshot 2024-03-20 at 6 30 22 PM](https://github.com/EddyKaggia/azure-fundamentals/assets/79530586/a5f64d5d-8359-4461-8e48-2b34276caac0)

You can use **Azure Traffic Manager**, a DNS-based traffic balancer, to fail-over from a failing _primary_ system to a stand-by _secondary_ system.

A common example is having a copy (_secondary_) of your database where all ongoing changes are synced. The _secondary_ system is not in use until a fail-over occurs and it becomes the _primary_ database.

## HIGH DURABILITY

The ability to **recover** from a disaster and to prevent **loss** of data. Solutions that enable recovery from a disaster are known as **_Disaster Recovery (DR)_**.

- Do you have a backup?
- How fast can you restore that backup?
- Does your backup still work?
- How do you ensure current live data is not corrupt?
