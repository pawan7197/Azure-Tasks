## Deploy Azure Application Gateway and Route Traffic to VMs:

## Table of Contents:

## Introduction:

Azure Application Gateway is a Layer 7 (Application Layer) load balancer that enables you to manage traffic to your web applications. It supports advanced routing features such as URL-based routing, SSL termination, and Web Application Firewall (WAF) capabilities.

## Key Components of Azure Application Gateway:

Component	              Description

Frontend IP	:     The IP address (Public or Private) where clients send    requests

Listener:	      Listens for incoming connection requests on the frontend IP 
and port

Backend Pool:	Group of backend servers (VMs, NICs, IPs, or App Services) that receive traffic

HTTP Settings:	Configuration for backend communication (protocol, port, session affinity)

Rules:          	Define how requests are routed from listener to backend pools

Health Probes:	Monitor the health of backend servers


**Lab Objectives:**

## Prerequisites:

**Step-by-Step Lab Guide**

Step 1: Create Resource Group

Step 2: Create Virtual Network and Subnets

Step 3: Deploy Virtual Machines

Step 4: Deploy Azure Application Gateway

Step 5: Configure Backend Pool

Step 6: Create HTTP Settings

Step 7: Create Listeners and Rules

Step 8: Test Application Gateway

## Summary:

**Cleanup:**

SSH key pair or password for VM authentication

## 1.  Step-by-Step Lab Guide:


## Step 1: Create a Resource Group:

Go to Azure Portal → Resource groups → Create.

Enter details:

Name: AppGatewayLabRG

Region: East US (or nearest)

Click Review + Create → Create.

## Step 2: Create Virtual Network and Subnets:


Navigate to Virtual networks → Create.

Enter details:

Name: AppGatewayVNet

Address space: 10.0.0.0/16

Add subnets:

AppGatewaySubnet: 10.0.1.0/24 (must be named this for gateway)

BackendSubnet: 10.0.2.0/24

Create the VNet.

## Step 3: Deploy Virtual Machines:

Create two Ubuntu VMs inside BackendSubnet.

Use SSH key or password authentication.

## Step-4: Application gateway:


Go to Create a resource → Search Application Gateway → Create.

Fill in details:

Name: AppGatewayDemo

Region: Same as VNet

Tier: Standard V2

SKU size: Small/Medium

VNet: AppGatewayVNet

Subnet: AppGatewaySubnet

Frontend IP: Assign Public IP

Create the gateway.

## Step 5: Configure Backend Pool:


Navigate to the created Application Gateway.

Go to Backend pools → Add.

Name it: AppGatewayBackendPool.

Add the NICs or IPs of both VMs.

Save.

## Step 6: Create HTTP Settings:


Go to HTTP settings → Add.

Name: AppGatewayHTTPSettings.

Settings:

Backend protocol: HTTP

Backend port: 80

Cookie-based affinity: Disabled (optional enable)

Health probe: Default (or custom at / on port 80)

Save.

## Step 7: Create Listeners and Rules:


Go to Listeners → Add listener.

Name: AppGatewayListener

Frontend IP: Public IP (created earlier)

Protocol: HTTP

Port: 80

Save.

Go to Rules → Add basic rule.

Name: AppGatewayRule

Listener: AppGatewayListener

Backend Pool: AppGatewayBackendPool

HTTP Settings: AppGatewayHTTPSettings

Save.

## Step 8: Test Application Gateway:


Copy the Public IP of the Application Gateway frontend.

Open a browser → Navigate to:
```
http://<AppGatewayPublicIP>
```

Refresh multiple times: You should see responses from VM1 and VM2 (round-robin).

## 6. Summary:

Component	Purpose
Resource Group	Logical container for resources
Virtual Network	Provides network segmentation
Subnets	Separate zones for gateway & backend
Virtual Machines	Backend servers hosting web apps
Application GW	Layer 7 load balancer for routing traffic
Backend Pool	Group of backend VMs
HTTP Settings	Defines communication with backend
Listener	Entry point for client requests
Rules	Maps listener → backend pool → HTTP settings

## 7. Cleanup:

Navigate to Resource Groups.

Delete AppGatewayLabRG.

This removes all resources and avoids ongoing charges.

## Images:

## 1.Virtual machine

<img width="1596" height="711" alt="Image" src="https://github.com/user-attachments/assets/09276535-e55f-4702-b322-65826960e4e6" />

## 2.App1 virtual machine

<img width="1591" height="738" alt="Image" src="https://github.com/user-attachments/assets/007c6484-613e-47cb-9f6b-e1639faa1b81" />

## 3. App1 server output 1

<img width="1584" height="747" alt="Image" src="https://github.com/user-attachments/assets/d81f91e7-373a-46e5-900a-265669dbb15b" />

## 4. App2 server virtual machine2

<img width="1597" height="720" alt="Image" src="https://github.com/user-attachments/assets/d9661a5e-ea34-4f86-a1c1-7c91db6c558b" />

## 5.App2 output

<img width="1599" height="732" alt="Image" src="https://github.com/user-attachments/assets/f76f5c53-b323-4bb9-a15b-9ae144d5d52b" />

## 6. Load balancing configure

<img width="1593" height="705" alt="Image" src="https://github.com/user-attachments/assets/2fb8c771-55c4-409d-b76f-dab5cbf679d9" />

## 7. Load balancer output

<img width="1599" height="715" alt="Image" src="https://github.com/user-attachments/assets/5135e95e-bf0a-4dba-8308-ccdfbe20fdae" />





✅ Lab Completed: Successfully deployed Azure Application Gateway, configured backend VMs, and routed traffic using Layer 7 load balancing.


## Author:

**Pawan Kumar Kothapalli**

**Azure Cloud Practitioner**

**Mail-Id:** pawankumarkothapalli22644@gmail.com

**LinkedIn** https://www.linkedin.com/in/pawan-kumar-kothapalli-17865b302/
