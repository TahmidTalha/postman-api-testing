# 🚀 API Testing Project using Postman & Newman

## 📌 Project Overview
This project demonstrates API testing using **Postman** and **Newman CLI**.  
It includes automated test execution of REST APIs along with HTML reporting for better analysis.

The project was created as part of my QA (Software Quality Assurance) learning and portfolio development.

---

## 🛠 Tools & Technologies Used
- Postman (API Testing)
- Newman (CLI for Postman)
- Node.js
- Git & GitHub
- HTML Extra Reporter (for reports)

---

## 📂 Project Structure# postman-api-testing


---

## ▶️ How to Run This Project

### 1. Install Newman globally
```bash
npm install -g newman
###2.Run API tests in terminal
newman run API_Testing.postman_collection.json -r htmlextra --reporter-htmlextra-export newman/report.html
