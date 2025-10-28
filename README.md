# Employee Management API Automation

This project automates CRUD operations for an **Employee Management API** using **Postman** and **Newman**, demonstrating end-to-end API testing workflows suitable for CI/CD pipelines.

---

## 🧪 Project Overview

- **API Base URL:** `https://api.restful-api.dev`
- **Endpoints Covered:**
  | Operation | Method | Endpoint |
  |-----------|--------|----------|
  | Create Employee | POST | /objects |
  | Get Employee by ID | GET | /objects/{{employeeId}} |
  | Update Employee | PUT | /objects/{{employeeId}} |
  | Delete Employee | DELETE | /objects/{{employeeId}} |
- **Features:**
  - Environment variable management (`employeeId`, `baseUrl`)  
  - Dynamic request chaining  
  - Assertions for status codes and response data  
  - CLI and HTML reporting via Newman  
  - CI/CD integration via GitHub Actions  

---

## ⚙️ How to Run Locally

1. **Install Node.js** (if not installed):  
   [Download Node.js](https://nodejs.org)

2. **Install Newman and HTML Reporter:**  
   ```bash
   npm install -g newman newman-reporter-htmlextra
   ```

3. **Run the Postman Collection:**  
   ```bash
   newman run Employee_Collection.postman_collection.json    -e Employee_Environment.postman_environment.json    -r cli,htmlextra    --reporter-htmlextra-export newman-report.html
   ```

4. **View HTML Report:**  
   Open `newman-report.html` in a browser to see detailed test results.

---

## 🔁 CI/CD Integration (GitHub Actions)

- Workflow file: `.github/workflows/api-tests.yml`  
- Runs automatically on:
  - Push to `main`  
  - Pull requests  
  - Manual triggers (workflow_dispatch)  

- Generates HTML report and uploads it as an artifact for review.  

**Example Badge (add to README):**
```markdown
![API Tests](https://github.com/<your-username>/<your-repo-name>/actions/workflows/api-tests.yml/badge.svg)
```
> Replace `<your-username>` and `<your-repo-name>` with your GitHub info.

---

## 📈 Optional Enhancements

- **Data-driven testing** with CSV or JSON  
- **Negative test scenarios** (invalid IDs, missing fields)  
- **Slack/Teams notifications** for test pass/fail  
- **Scheduled runs** via Postman Monitors  
- **Parallel execution** for large collections  

---

## 🗣 How to Explain in Interviews

> “I designed an end-to-end API automation project using Postman for CRUD operations on an Employee Management System.  
> I implemented environment variable chaining, assertions, CLI automation with Newman, HTML reporting, and CI/CD integration with GitHub Actions.  
> The setup validates API functionality automatically on every commit or pull request, simulating real-world regression testing workflows.”
