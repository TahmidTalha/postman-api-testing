# 🚀 Restful Booker API Testing Project

## 📌 Project Overview

This project demonstrates end-to-end API testing of the Restful Booker REST API using Postman and Newman.

The collection covers the complete booking lifecycle, including authentication, booking creation, retrieval, update, and deletion. Automated assertions are implemented to validate API responses, response times, data integrity, and CRUD operations.

The project also utilizes dynamic test data generation and environment variables to create realistic test scenarios and reduce hardcoded values.

---

## 🎯 Objectives

* Validate REST API functionality
* Verify CRUD operations
* Perform automated API testing using Postman
* Execute collections using Newman CLI
* Generate HTML execution reports
* Practice environment and variable management
* Implement response validation and data verification

---

## 🛠 Tools & Technologies

* Postman
* Newman
* Newman HTML Extra Reporter
* JavaScript (Postman Test Scripts)
* Git
* GitHub

---

## 🌐 API Under Test

**Restful Booker API**

Base URL:

```text
https://restful-booker.herokuapp.com
```

---

## 📂 Project Structure

```text
API_Testing.postman_collection.json
API_Testing.postman_environment.json
README.md
newman/
 └── HTML execution reports
```

---

## 🔄 Test Workflow

The collection executes the following workflow:

### 1. Create Authentication Token

**Endpoint**

```http
POST /auth
```

**Validations**

* Token is generated successfully
* Token exists in response
* Token data type is string

---

### 2. Get All Booking IDs

**Endpoint**

```http
GET /booking
```

**Validations**

* Status code = 200
* Response time < 2000 ms
* Every booking contains a valid booking ID

---

### 3. Create Booking

**Endpoint**

```http
POST /booking
```

**Dynamic Data Generation**

* Random First Name
* Random Last Name
* Random Total Price
* Random Deposit Status
* Dynamic Check-in Date
* Dynamic Check-out Date

**Validations**

* Status code = 200/201
* Response time < 2000 ms
* First Name validation
* Last Name validation
* Total Price validation
* Deposit Paid validation
* Check-in validation
* Check-out validation
* JSON response validation

**Output**

* Booking ID stored in environment variable

---

### 4. Get Created Booking

**Endpoint**

```http
GET /booking/{{id}}
```

**Validations**

Verify status code is 200
Verify response time is less than 2000 ms
Validate booking details match the created data:
First name
Last name
Total price
Deposit value
Check-in date
Check-out date

---

### 5. Update Booking

**Endpoint**

```http
PUT /booking/{{id}}
```

**Authentication**

* Token-based authorization

**Validations**

* Status code = 200
* Response time < 2000 ms
* Updated booking data verification
* JSON response validation

---

### 6. Verify Updated Booking

**Endpoint**

```http
GET /booking/{{id}}
```

**Validations**

* Updated data persists correctly
* Response values match environment variables

---

### 7. Delete Booking

**Endpoint**

```http
DELETE /booking/{{id}}
```

**Authentication**

* Token-based authorization

**Validations**

* Status code = 200

---

### 8. Verify Booking Deletion

**Endpoint**

```http
GET /booking/{{id}}
```

**Validations**

* Status code = 404
* Booking no longer exists

---

## ✅ Assertions Implemented

The project includes automated validations for:

* Status Code Verification
* Response Time Validation
* Response Body Validation
* Data Type Validation
* Environment Variable Validation
* JSON Response Validation
* CRUD Workflow Verification
* Authentication Verification
* Booking Data Integrity Validation

---

## 🔐 Environment Variables

The following variables are dynamically managed:

| Variable   | Purpose              |
| ---------- | -------------------- |
| baseUrl    | API Base URL         |
| token      | Authentication Token |
| id         | Booking ID           |
| firstName  | Generated First Name |
| lastName   | Generated Last Name  |
| totalPrice | Booking Price        |
| deposit    | Deposit Status       |
| checkin    | Check-in Date        |
| checkout   | Check-out Date       |

---

## ▶️ How to Run This Project

### Install Newman

```bash
npm install -g newman
npm install -g newman-reporter-htmlextra
```

### Execute Collection

```bash
newman run API_Testing.postman_collection.json
```

### Generate HTML Report

```bash
newman run API_Testing.postman_collection.json -r htmlextra --reporter-htmlextra-export newman/report.html
```

---

## 📊 Test Reports

Execution reports are automatically generated in the `newman` folder using the Newman HTML Extra Reporter.

---

## 👨‍💻 Author

**Tahmid Mostaque Talha**

Software Engineering Graduate | QA Engineer | API Testing Enthusiast
