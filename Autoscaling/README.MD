## 🧪 Lab: Deploy Azure Virtual Machine Scale Set (VMSS):

## 📌 Objective:

Deploy a Virtual Machine Scale Set (VMSS) in Azure with:

Ubuntu Linux virtual machines

Startup script to install Apache web server

Azure Load Balancer

Autoscale rules based on CPU utilization

## 🧱 Steps to Deploy VMSS:

**1. Create a VMSS:**

Log in to Azure Portal

Search for Virtual Machine Scale Sets → Click Create

Basics Tab

Subscription: Your active subscription

Resource Group: VMSSLabRG

Name: MyVMSS

Region: East US (or any zone-redundant region)

Orchestration Mode: Uniform

Image: Ubuntu Server 20.04 LTS

Authentication: Password or SSH Key

Username: azureuser

Instances Tab

Instance Count: 2

Availability: Zone redundant

VM Size: Standard B1s

Disks Tab

Keep default OS disk settings

Networking Tab

Virtual Network: New or existing

Public IP: Enabled

Load Balancer: Azure Load Balancer

Inbound Ports: Allow HTTP (80) and SSH (22)

Scaling Tab

Enable Autoscaling

Min Instances: 2

Max Instances: 5

Scale Out: CPU > 70%

Scale In: CPU < 30%

Custom Data (Startup Script)

## Add the following script under Advanced → Custom Data:
```
#!/bin/bash
sudo apt -y update
sudo apt -y install nginx
sudo systemctl start nginx
sudo systemctl enable nginx
echo "git installed"
sudo rm -rf /var/www/html*
sudo git clone https://github.com/Ai-TechNov/mario.git /var/www/html/
```


Click Review + Create → Create

## 2. Test the Deployment:

Go to VMSS Overview → Copy the Public IP from the Load Balancer

Open in browser:
```

http://<public-ip>
```


## ✅ You should see: Welcome to Azure VM Scale Set!

## 3. Test Autoscaling (Optional):


SSH into one VM instance and install stress tool:
```
sudo apt install stress -y
stress --cpu 1 --timeout 300
```

If CPU > 70%, new instances will be added automatically.

4. Clean Up (Avoid Charges)

## Delete the resource group:

az group delete --name VMSSLabRG --yes --no-wait

## ✅ Lab Summary:

Task	Status

Deploy VMSS	✅

Install web app via startup script	✅

Configure Load Balancer	✅

Setup Autoscaling	✅

Access Public Website	✅

## Author: 

**Pawankumar Kothapalli****

**Azure Cloud Practioner**


**Gmail:**  pawankumarkothapalli22644@gmail.com

**LinkedIn:**  https://www.linkedin.com/in/pawan-kumar-kothapalli-17865b302/
