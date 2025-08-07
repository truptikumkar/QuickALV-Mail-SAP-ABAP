# 📧 QuickALV-Mail 
*An SAP ABAP Mini Project for Automated Stock Report Emailing*

---

## 🔍 Project Description  
**ALV-StockMail-Automation** is an SAP ABAP mini project that automates the generation of material stock status reports in ALV (ABAP List Viewer) format and delivers them via email to internal SAP users and external business stakeholders. The process can be scheduled to run periodically using background job scheduling (SM36), eliminating manual report generation and sharing.

---

## 🚀 Key Features  
- ✅ Fetch stock data from custom SAP table `ZTABLE_REQ`  
- 📊 Display structured ALV report with field-level formatting  
- 📧 Auto-generate and send emails with Excel attachments  
- 👥 Support for multiple recipients (SAP users & external emails)  
- 📎 Excel attachment creation using `SCMS_TEXT_TO_BINARY`  
- ⏰ Scheduled execution using background jobs  
- 💬 Customizable email body and subject line  
- 🔄 Robust exception handling  

---

## 🛠️ Technologies & Concepts Used  

| Component / Class        | Description                                       |
|--------------------------|---------------------------------------------------|
| `REUSE_ALV_GRID_DISPLAY` | ALV Report display in classic format             |
| `CL_BCS`                 | Core class to build and send email               |
| `CL_DOCUMENT_BCS`        | Create email body and attach content             |
| `CL_CAM_ADDRESS_BCS`     | Add external recipients (internet email)         |
| `CL_SAPUSER_BCS`         | Add internal SAP user as recipient               |
| `SCMS_TEXT_TO_BINARY`    | Convert report to binary (Excel-compatible)      |
| Background Job (`SM36`)  | Schedule report + email to run periodically      |

---

## 📌 Workflow Overview  

### User Input:  
Input parameters collected through `SELECT-OPTIONS` (e.g., Request Number, Posting Date) and checkbox `SEND_M`.

### Data Fetching:  
Data retrieved from the custom table `ZTABLE_REQ` based on input filters.

### ALV Report Display:  
Uses classic ALV function module `REUSE_ALV_GRID_DISPLAY` to present the report interactively.

### Email Trigger:  
If the `SEND_M` checkbox is selected, the system:  
- Formats ALV data into internal tables  
- Converts the table to Excel (binary)  
- Builds an email body  
- Attaches the report as `.XLS` file  
- Sends to SAP user and external recipients  

### Scheduling:  
Can be scheduled via transaction `SM36` to execute periodically.

---

## 👨‍💻 Author  
**Kunal Deshpande**  
SAP ABAP Developer Intern  
📧 kunalgirish135@gmail.com  

---

## 🏁 How to Run  
1. Upload the ABAP report (`ZTESTMP_REPORT`) into the SAP system.  
2. Maintain the custom table `ZTABLE_REQ` with relevant data.  
3. Run the report with appropriate filters.  

To automate email sending:  
- Check the `SEND_M` parameter.  
- Or schedule the program using `SM36` for background execution.  

📧 Email with the ALV report will be sent to configured recipients.

---

## 📸 Screenshots  

<img width="1365" height="717" alt="image" src="https://github.com/user-attachments/assets/bc24f2e6-caa4-495d-96a2-508f860c0778" />

<img width="1365" height="659" alt="image" src="https://github.com/user-attachments/assets/803b9703-ed80-4ef0-ac61-f27eacb46d40" />

<img width="1365" height="674" alt="image" src="https://github.com/user-attachments/assets/365d408a-dd03-4b89-92ec-1936e71ed85f" />

---

## ✅ Future Improvements  
- Implement HTML email formatting for better readability  
- Allow dynamic recipient selection via input screen  
- Support multiple file formats (e.g., PDF)  
- Track email delivery status using SAP logs

### 👨‍💻 Author
Trupti kumkar
SAP ABAP Developer 
