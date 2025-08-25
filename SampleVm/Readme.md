
# Create an Azure VM and Deploy a Sample App

## Part 1: Create the Virtual Machine
1. **Log into the Azure Portal**
2. Navigate to **Virtual machines** > Click **+ Create** > **Azure virtual machine**
3. **Basics tab:**
   - **Subscription:** Select your Azure subscription
   - **Resource group:** Create or select an existing one (e.g., `LabRG`)
   - **Virtual machine name:** `SampleVM`
   - **Region:** Choose one near you
   - **Image:** `Ubuntu 22.04 LTS`
   - **Size:** e.g., `Standard B1s` (cheap and good for testing)
   - **Authentication type:** SSH public key (recommended) or password
   - **Username:** `azureuser`
   - **SSH key:** Generate or paste your public key

4. **Disks tab:** Leave default (Premium SSD or Standard SSD)

5. **Networking tab:**
   - Use default virtual network and subnet
   - **Public IP:** Yes (for remote access)
   - **NIC network security group (NSG):**
     - Allow SSH (port 22)
     - Click "Add inbound port rule" > Allow HTTP (port 80)

6. **Management, Monitoring, and Advanced:** leave defaults (or disable diagnostics if not needed)
7. Click **Review + create** > **Create**
   - Wait for deployment to complete (1–2 minutes).

## Part 2: Connect to the VM via SSH
1. Get the public IP address from the VM overview page.
2. Open a terminal and connect:
   ```bash
   ssh azureuser@<your-public-ip>
   ```
   If you're using Windows and don't have a native terminal, use PuTTY or Windows Terminal with WSL.

## Part 3: Lab Steps

### Step 1: Update Package Repository
```
sudo apt update
```

### Step 2: Install Nginx
```
sudo apt install nginx -y
```

### Step 3: Start Nginx Service
```
sudo systemctl start nginx
```

### Step 4: Enable Nginx on Boot
```
sudo systemctl enable nginx
```

### Step 5: Verify Nginx Service Status
```
systemctl status nginx
```
You should see **Active: running** in green.

### Step 6: Configure Firewall (if enabled)
```
sudo ufw allow 'Nginx HTTP'
sudo ufw status
```

### Step 7: Verify Installation in Browser
- Get your server’s IP:
  ```
  hostname -I
  ```
- Open a web browser and go to:
  ```
  http://<your-server-ip>
  ```
You should see the **Nginx Welcome Page**.

## Useful Nginx Commands
| Action       | Command                        |
|--------------|--------------------------------|
| Start Nginx  | sudo systemctl start nginx     |
| Stop Nginx   | sudo systemctl stop nginx      |
| Restart      | sudo systemctl restart nginx  |
| Reload Config| sudo systemctl reload nginx   |
| Check Status | systemctl status nginx        |

## Part 4: Test Your App
- Open your browser
- Navigate to: `http://<your-public-ip>`
- You should see the **Welcome to Azure VM Web App** page 🎉
## Images
## 1. Create virtual machine

<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/13f2d9fa-0d6a-4989-ae60-9840b6d8fc28" />



## 2. Create SSH command

<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/6664c7c9-e16b-41f4-822a-b096c9d10d37" />

## 3. NGINX status

<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/5e8f924e-d701-4efe-a722-d35194efd5df" />

## 4. Output of sample VM

<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/38908f63-d83e-453b-aef9-f5b11862fe11" />

## Optional: Clean Up
To avoid charges:
- Stop or delete the VM
- Delete the resource group (`LabRG`) to remove everything


  ## Author:

  **Pawankumar Kothapallli**
  
  **Azure cloud Practitioner**
  
  **LinkedIn-URL:**   https://www.linkedin.com/in/pawan-kumar-kothapalli-17865b302/
  
  **Mail-Id: **  pawankumarkothapalli22644@gmail.com
