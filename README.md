# Performance Testing with Apache JMeter
This project contains performance and load tests executed using Apache JMeter.
It includes ready-to-run JMX test plans, result generation, and an automated HTML performance report.

---

# 📌 Project Structure
```bash 
performance-jmeter/
│
├── jmeter/
│   ├── test-plans/               # JMeter .jmx test plans
│   ├── results/                  # Raw JTL results (auto-generated)
│   └── reports/                  # HTML performance reports (auto-generated)
│
├── data/                         # Optional JSON/CSV test data
├── environments/                 # Environment configs if needed
└── README.md
```
---

# 🚀 How to Run the Tests Locally
1. Install Apache JMeter

Download the latest version of JMeter:
https://jmeter.apache.org/download_jmeter.cgi

Unpack the archive and verify JMeter runs:
```bash
jmeter --version
```

---

# Run a Test Plan

From the project's root directory:
```bash
jmeter -n -t jmeter/test-plans/reqres-smoke.jmx \
       -l jmeter/results/reqres-smoke.jtl \
       -e -o jmeter/reports/reqres-smoke
```
This command does the following:

-n → run in non-GUI mode

-t → specify test plan

-l → write raw results

-e -o → generate HTML dashboard report

---

# 📊 Viewing the Report

After execution, open:
```bash
jmeter/reports/reqres-smoke/index.html
```
This file contains:

APDEX score

Response time distribution

Throughput

Errors & failures

Percentiles (50th, 90th, 95th, 99th)

---

# 🧪 Test Scenario

The test plan uses the Reqres API and performs:

GET List Users

Response validation

Load simulation

Error tracking

You can modify or scale the test in the JMX plan.

---

# 🔧 Requirements

Java 8 or higher

Apache JMeter

(Optional) JSON/CSV input files stored in /data

---

## 📝 Notes

If you see 401 Unauthorized, ensure your API does not require authentication.

Clean previous results before running new tests.

You can scale load using Thread Group parameters.

---

## 📄 License

This project is provided for educational and testing purposes.
