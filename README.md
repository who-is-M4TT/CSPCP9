# CSPCP9

📌 Overview
This project deploys a multi-service Docker app (React + Express + MongoDB) on an Azure VM, integrates with an Azure Function (serverless) for event-driven processing, and uses Azure Blob Storage.

---

## 🔄 Service Flow & Integration Points
1. React Frontend (Docker)
   - Runs in a container on Azure VM.
   - Provides user interface for managing products and stock.

2. Express Backend (Docker)
   - Handles REST API requests from frontend.
   - Connects to MongoDB for product/stock storage.
   - Triggers **Azure Function** when stock is low.

3. MongoDB (Docker)  
   - Stores product catalog and inventory data.
   - Runs inside VM as part of the Docker Compose stack.

4. Azure Function (Serverless) 
   - Triggered by backend HTTP POST requests.
   - Processes low-stock events.
   - Logs audit events in **Azure Blob Storage**.
   - Sends notifications (via Logic Apps).

5. Azure Blob Storage 
   - Stores JSON audit logs for tracking low-stock events.
