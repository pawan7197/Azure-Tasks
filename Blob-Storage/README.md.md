# 🚀 Project: Azure Storage Blob Public Access Setup

## 🎯 Objective  
Learn how to create a container in Azure Storage Account, upload files, configure access settings, and retrieve the file URL for public access.

---

## 🛠 Prerequisites  
- Active Azure subscription  
- Azure Storage Account created  
- Proper permissions to manage storage resources

---

## ⚡ Steps

### 1️⃣ Create and Configure Storage Container
1. Login to the [Azure Portal](https://portal.azure.com).
2. Navigate to your **Storage Account**.
3. Click **Data Storage → Containers**.
4. Click **+ Container** to create a new container.
5. Enter a **Container Name** (e.g., `mycontainer`).
6. Set **Public access level** to `Private (no anonymous access)`.
7. Click **Create**.

---

### 2️⃣ Upload Files to Container
1. Open the created container from the container list.
2. Click **Upload**.
3. Browse and select the file(s) to upload from your local system.
4. Enable **Allow blob anonymous read access for blobs only**.
5. Click **Upload**.

---

### 3️⃣ Configure Access Level for Container
1. Click **Change access level** in the container menu.
2. Select **Blob (anonymous read access for blobs only)** from the dropdown.
3. Click **Save**.

---

### 4️⃣ Get File URL for Public Access
1. Open the uploaded file from the container.
2. Click **Copy URL**.
3. Open a new browser tab and paste the URL.
4. The file should open publicly in the browser.

---

## ✅ Result  
File is now publicly accessible via the copied URL.