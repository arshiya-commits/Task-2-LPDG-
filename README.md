# 🚦 Traffic Velocity Anomaly Detection  

This project analyzes a traffic dataset (CSV with timestamps & velocities) to detect anomalies in vehicle speed patterns.  

---

## 📌 Objective  
- Compare each row’s velocity to the previous timestamp’s velocity  
- Mark rows as **Normal** or **Anomaly**  

---

## 🛠️ Steps Performed  
- Load the dataset  
- Convert timestamps to datetime  
- Sort the dataset by datetime  
- Compare with previous row (`delta_v`, `delta_t`)  
- Apply anomaly rules (`velocity < 0` or big jump in <0.5s)  
- Save results with a `status` column  

---

## 📊 Future Model Note  
- Train model on Normal data  
- Validate using Anomaly rows  
- Use for semi-supervised anomaly detection  

---

## ⚡ Tech Stack  
- Python 🐍  
- Pandas  

---

## 🚀 How to Run  
```bash
pip install pandas
python [filename].py
