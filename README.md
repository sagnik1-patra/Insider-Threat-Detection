#  Insider Threat Detection System

This project aims to detect insider threats using user activity patterns and unsupervised machine learning. It identifies users with unusual behavior and classifies them as:

- **Careless Insider**
- **Malicious Insider**
- **Compromised Account**

---

##  Project Structure

Insider Threat Detection/
│
├── threat_users.csv
├── high_risk_users.csv
├── activity_log.csv
├── Screenshot 2025-08-01 234142.png
├── insider_threat_detection.ipynb
└── README.md

yaml
Copy
Edit

---

##  How It Works

### 1. Load User Features
User behavior features are loaded from `threat_users.csv`.

### 2. Dimensionality Reduction
UMAP is used to reduce high-dimensional behavior patterns into 2D for clustering.

### 3. Clustering
DBSCAN algorithm identifies groups of similar behavior. Outliers are marked as threats.

### 4. Threat Classification
Predicted labels:
- `Careless Insider`
- `Malicious Insider`
- `Compromised Account`

Sample Output:
Predicted Threat Label Counts:

Careless Insider 43
Malicious Insider 4
Compromised Account 3

yaml
Copy
Edit

---

##  High-Risk Users

A list of high-risk users is saved in `high_risk_users.csv`.

**Sample:**

| user_id  | predicted_label     |
|----------|---------------------|
| user_10  | Malicious Insider   |
| user_23  | Compromised Account |
| user_30  | Malicious Insider   |

---

##  Activity Log Generation

If not provided, a simulated `activity_log.csv` is generated automatically with:

- 50 logs/user
- Activities like `login`, `file_access`, `usb_connect`
- Random timestamps, devices, and locations

---

##  Screenshot

Below is a sample visualization of clustering results:

![Threat Detection Screenshot](Screenshot%202025-08-01%20234142.png)

---

##  Further Analysis Ideas

-  Merge `high_risk_users.csv` with `activity_log.csv`
   Analyze login times (e.g., off-hours logins)
-  Check for excessive file access
-  Monitor geolocation anomalies

---

##  Technologies Used

- Python (Pandas, Scikit-learn, UMAP, Seaborn)
- Jupyter Notebook
- DBSCAN for unsupervised threat detection
