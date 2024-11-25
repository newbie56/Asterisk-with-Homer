# **Call Monitoring using Homer**

## **Configure Asterisk Server and SIP Clients**

### **1. Configure Users and Dialplan**
- **Edit PJSIP Users**  
  Update the configuration for SIP users in `/etc/asterisk/pjsip.conf`.

- **Edit Dialplan**  
  Configure the dialplan in `/etc/asterisk/extensions.conf`.

- **Configure HEP for Homer**  
  If you are using Homer to capture call data, ensure the capture address points to the target server's IP and port in `/etc/asterisk/hep.conf`.  
  Example:  
[general]
capture_address = 10.8.0.159:9060

![image](https://github.com/user-attachments/assets/2ac9f8a9-d184-4b9f-89e2-80e1d944b4f1)

### **2. Configure SIP Clients**
- Input the correct **username** and **password** in your SIP client settings as specified in the Asterisk configuration.

user 7001
![image](https://github.com/user-attachments/assets/259d4f0c-8cda-46d9-a5be-a3762956a33d)
---
user 7002
![image](https://github.com/user-attachments/assets/f66a4124-58f7-4a87-bc7f-62213be76f59)
---

### **3. Start Asterisk**
- Use the following command to start Asterisk:
```bash
asterisk -cvvvvv
```
- If Asterisk is already running, connect to the console with:
```bash
asterisk -r
```
Ensure the necessary modules are loaded for HEP to function properly:
```bash
module load res_hep.so
module load res_hep_pjsip.so
module load res_hep_rtcp.so
module load func_channel.so
```

### **3. Access Monitoring Tools**
Once the call is initiated, you can view monitoring details.
![Screenshot 2024-11-25 154344](https://github.com/user-attachments/assets/6e8e1e85-f6a2-47d7-970a-30d1254299bb)

a. Homer
- Homer provides detailed call analytics and packet capture data.
![Screenshot 2024-11-25 154506](https://github.com/user-attachments/assets/ee822d65-b394-4158-b4fe-b2b57c6a18e0)

b. Grafana
- Grafana can be configured to visualize call metrics.
![Screenshot 2024-11-25 154717](https://github.com/user-attachments/assets/21252ac7-7918-4496-9a54-bbfe033e2dd1)

