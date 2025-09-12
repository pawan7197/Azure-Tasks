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

## Images
1. Storage account

<img width="1589" height="703" alt="Image" src="https://github.com/user-attachments/assets/0b692836-771f-4ffe-b048-ff5ba2951441" />

2. Created a container

<img width="1599" height="568" alt="Image" src="https://github.com/user-attachments/assets/76654986-8283-47c4-ab0f-1a80daa26cf7" />

3. Files uploaded

<img width="1599" height="558" alt="Image" src="https://github.com/user-attachments/assets/21dac282-5a37-4d7f-b924-f5a5767c2b41" />

4. Enable Allow blob anonymous read access

<img width="877" height="448" alt="Image" src="https://github.com/user-attachments/assets/00629e2e-27ab-45c9-91f3-d4f9d1dfab1e" />

5. Click **Change access level** in the container menu

<img width="1599" height="474" alt="Image" src="https://github.com/user-attachments/assets/00208df0-96f2-4c5d-807f-c63512dced9e" />

6. Copy URL of file1

<img width="1571" height="258" alt="URL copy 1" src="https://github.com/user-attachments/assets/b5133045-de25-4690-a66b-03582b202c17" />

7. Paste the  URL in new tab and the file should open publicly in the browser

<img width="1599" height="835" alt="output1" src="https://github.com/user-attachments/assets/cee6ec0c-00b7-43b9-a960-7c989542c9cb" />

8. Copy URL of file2

<img width="1581" height="325" alt="URL copy2" src="https://github.com/user-attachments/assets/0ae6598b-cf9d-4692-95b4-af7e38ba0bdc" />

9. paste the URL in new tab and the file should open publicly in the browser

![pic](https://github.com/user-attachments/assets/8ace6fa2-e0e4-4c6f-a3c6-9e6a252a0d6c)


## ✅ Result  
File is now publicly accessible via the copied URL.

Author:
Pawankumar Kothapalli**

Azure Cloud Practioner

Gmail: pawankumarkothapalli22644@gmail.com

LinkedIn: https://www.linkedin.com/in/pawan-kumar-kothapalli-17865b302/
