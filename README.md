# VSFTPD Backdoor Detection  
Detecting **VSFTPD 2.3.4 Backdoor Exploits** via **Network Traffic Analysis** and **Machine Learning**.

---

## 📖 Project Overview  
This project focuses on detecting the **VSFTPD 2.3.4 backdoor exploit** through network traffic analysis and machine learning.  
It simulates attacks using **Metasploit**, captures traffic using **Wireshark**, and trains a **Random Forest Classifier** to distinguish between normal and malicious FTP activity.

---

## 🛠️ Tools & Technologies  
- 💥 **Metasploit Framework** – for attack simulation  
- 🧪 **Wireshark / Tshark** – for traffic capture and CSV conversion  
- 🐍 **Python** – for data processing and modeling  
- 📊 **Scikit-learn** – used for Random Forest classification  

---

## ⚙️ Project Setup  

### 2️⃣ Capture Traffic  
- Use **Wireshark** to capture traffic on ports `21` (FTP) and `6200` (backdoor).  
- Export `.pcap` files and convert to `.csv` using `tshark`.

---

### 3️⃣ Data Preprocessing  
Extract and prepare these features:
- `frame_len`  
- `tcp_dstport`  
- `protocol`  
- `time_diff`  

Apply **one-hot encoding** to categorical features.

---

## 🧠 4. Training the Model  
We used the **Random Forest Classifier** to detect malicious FTP backdoor traffic:

```python
from sklearn.ensemble import RandomForestClassifier
clf = RandomForestClassifier()
clf.fit(X_train, y_train)
```

---

## 📈 5. Evaluation
Performance metrics on test data:
* **Accuracy:** 88%
* **ROC AUC Score:** 91%
* **F1-Score (Attack):** 0.89

---

## 📊 6. Results
The trained model effectively detects malicious FTP backdoor traffic with:
* ✅ **High precision**
* ✅ **Low false positive rate**

---

## 🔍 7. Key Features
* 🔁 Realistic attack simulation
* 🌐 Network traffic classification using machine learning
* 🧠 Robust feature engineering
* 🚦 Clear separation between normal and attack traffic

---

## 📂 8. Dataset
* **140 packets captured**, including both *normal* and *attack* traffic
* Labels derived from:
   * ⏱️ **Timing**
   * 🎯 **Destination Ports**: `21` (FTP), `6200` (backdoor)

---

## 📢 9. License
This project is for **educational** and **ethical cybersecurity research** purposes only.
