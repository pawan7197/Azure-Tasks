
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

## Optional: Clean Up
To avoid charges:
- Stop or delete the VM
- Delete the resource group (`LabRG`) to remove everything
