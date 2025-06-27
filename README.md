# 🤖 UiPath_CalculateClientSecurityHash_Performer
This is the **Performer** part of the Calculate Client Security Hash RPA project using **UiPath REFramework**.  
It retrieves queue items containing client information, calculates a security hash, and updates the ACME System 1 Work Items accordingly.

## 📌 Project Purpose
Automate the process of validating and updating client work items by calculating a unique hash based on client data and entering it into the ACME System 1 portal.

## 🔍 What It Does
1. Gets transaction items from the Orchestrator Queue.
2. Opens [ACME System 1](https://acme-test.uipath.com).
3. Extracts from queue:
   - Client ID
   - Client Name
   - Client Country
4. Calculates **Security Hash** using SHA256 on:  
   `ClientID + ClientName + ClientCountry`
5. Submits the hash value on the website.
6. Updates the work item status:
   - **Completed** if successful
   - **Failed** if any error occurs
   - 
## 🧰 Technologies Used
- UiPath Studio
- REFramework
- Orchestrator Queue
- ACME Test Website
- SHA256 hashing
- Config file and Assets

## 🚀 How to Run
1. Make sure the Dispatcher has populated the queue.
2. Update `Config.xlsx` with:
   - ACME URL
   - ACME Workitems URL
   - SHA URL
   - Queue name
   - Credential name (from Orchestrator Assets)
3. Run `Main.xaml`

## 🧪 REFramework Used
- Transactional process with retry mechanism
- Logging via Log Message
- Exception handling through Try/Catch
- QueueItem-based processing
