# APIs_Automation_Coding_Challenge_
Project work
### **Marketstack API Test Report**

**Date of Testing**: 10/30/2024 
**Tested By**: Henry okolie 

---

### **Summary**

| **Test Component**             | **Status**     | **Details**                                                                                   |
|--------------------------------|----------------|-----------------------------------------------------------------------------------------------|
| **Iterations**                 | **1**          | Completed without errors                                                                     |
| **Total Requests**             | **10**         | All requests successful                                                                      |
| **Test Scripts Executed**      | **19**         | All scripts passed                                                                           |
| **Pre-request Scripts**        | **18**         | No failures                                                                                  |
| **Assertions**                 | **56**         | All assertions passed without issues                                                         |
| **Total Run Duration**         | **8.5s**       |                                                                                               |
| **Total Data Received**        | **102.8 kB**   |                                                                                               |
| **Average Response Time**      | **789 ms**     | [Range: 139 ms - 3.9 s; Std. Dev: 1.155 s]                                                   |
| **Average DNS Lookup Time**    | **45 ms**      | [Stable, min/max: 45 ms]                                                                     |
| **Average First Byte Time**    | **762 ms**     | [Range: 136 ms - 3.9 s; Std. Dev: 1.153 s]                                                   |

---

### **Detailed Test Results**

1. **GET End-of-Day Data Endpoint**
   - **URL**: `https://api.marketstack.com/v1/eod?symbols=AAPL&access_key=[your_key]`
   - **Response**: 200 OK
   - **Time**: 522 ms
   - **Size**: 27.62 kB (JSON data)
   - **Validation**:
     - Pagination object structure was valid.
     - Open, high, low, close, and volume fields had non-negative values.
     - **All tests passed**.

2. **Intraday Data Endpoint**
   - **URL**: `https://api.marketstack.com/v1/intraday?symbols=AAPL&access_key=[your_key]`
   - **Response**: 200 OK
   - **Time**: 165 ms
   - **Validation**:
     - Required fields (`timezone`, `abbr`, `abbr_dst`) present and non-empty.
     - Content-Type header validated.
     - **All tests passed**.

---

### **Performance Observations**

- **Average Response Time**: 789 ms; some variability noted, with one response time reaching up to 3.9 seconds.
- **Response Time Target**: 522 ms for primary requests; further optimization suggested to consistently keep response times under 500 ms.
  
---

### **Conclusion**

The Marketstack API performed reliably under test, with accurate and consistent responses across endpoints. All validation checks were met, though occasional delays in response time indicate potential for further optimization.
**Observation**

During testing, it was noted that the response time for several endpoints exceeded the standard threshold (500 ms). This delay in response impacted real-time data retrieval and could affect the performance of applications relying on the Marketstack API for quick data updates. Further investigation may be needed to identify the cause and optimize response times.

