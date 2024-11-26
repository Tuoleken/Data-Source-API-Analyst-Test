# **Data-Source-API-Analyst-Test**

This repository contains the solution for the **homework assignment** for the _Data Source API Analyst_ role. The project focuses on interacting with the **GitHub REST API** to extract data related to repositories, commits, and contents. The implementation demonstrates proficiency in API interaction, troubleshooting, and proper documentation.

---

## **Repository Structure**
/Content - 1) API_Documentation.md: Details of the GitHub API endpoints used. 
         - 2) Troubleshooting_Guide.md: Solutions for common issues during API interaction. 

/Postman_Collection - Github_API_Test.postman_collection.json: Postman collection containing API requests.


---

## **Task Breakdown**

### **Step 1: Prepare & Test a List of Reports**

#### **Client Needs**  
The client required data extraction for the following:  
1. **Search Public Repositories**: _Retrieve a list of public repositories for a given user or organization._  
2. **Commits**: _Fetch commit history for specific repositories._  
3. **Contents**: _Retrieve the content of a file or directory within a repository._  

#### **API Research**  
Key considerations during API research included:  
- **Requests Logic**: Understanding required parameters and response structures.  
- **Pagination**: Managing results spread across multiple pages.  
- **Rate Limits**: Monitoring API limits and handling retries.  
- **Authentication**: Using a personal access token for secure access.  

_Refer to `API_Documentation.md` for endpoint details and sample responses._

---

### **Step 2: Set Up a GitHub Repository**

1. **Repository Name**: `Data-Source-API-Analyst-Test`  
2. **Description**: _"Homework assignment for the Data Source API Analyst role."_  
3. **Visibility**: **Public**  

**Structure**: Organized into `/Content` for documentation and `/Postman_Collection` for API requests.  

---

### **Step 3: API Extraction via Postman**

1. **Environment Setup**  
   A Postman environment named `GitHub` was created with the following variables:  
   - `base_url`: `https://api.github.com`  
   - `username`: _GitHub username._  
   - `auth_token`: _Personal access token with appropriate permissions._  

2. **API Endpoints**  
   Configured and tested the following:  
   - **Search Public Repositories**: `/users/{username}/repos`  
   - **Repository Commits**: `/repos/{owner}/{repo}/commits`  
   - **Repository Contents**: `/repos/{owner}/{repo}/contents/{path}`  

3. **Pagination and Rate Limits**  
   - Pagination handled using the `page` and `per_page` query parameters.  
   - Rate limits monitored via headers: `X-RateLimit-Remaining` and `X-RateLimit-Reset`.  

4. **Response Testing**  
   - Verified and saved response samples for correctness.  

---

### **Step 4: Troubleshooting Guide**

_Common issues and their solutions are documented in `/Content/Troubleshooting_Guide.md`._  

**Example**:  
- **401 Unauthorized Error**:  
   - **Check Authentication**: Ensure the `auth_token` is valid and has necessary permissions.  
   - **Verify Environment Variables**: Make sure the environment variables in Postman are correctly set.  
   - **Monitor Rate Limits**: Apply retries if necessary.  

---

### **Step 5: Results**

1. **Postman Collection Export**  
   The requests are saved in the Postman collection file:  
   `/Postman_Collection/Github_API_Test.postman_collection.json`.  

2. **Reflection**  
   - This task demonstrated the ability to effectively interact with REST APIs using Postman.  
   - Postman provided an intuitive interface for testing and troubleshooting requests.  

---

## **How to Use**

1. Clone this repository:  
   ```bash
   git clone https://github.com/your-username/Data-Source-API-Analyst-Test.git
2. Import the Postman collection file from /Postman_Collection into Postman.
3. Set up the GitHub environment with your credentials (auth_token, username).
4. Test the configured API endpoints or modify them as needed.

## **References**

- [GitHub REST API Documentation](https://docs.github.com/rest)  
- [Postman Documentation](https://learning.postman.com/docs/getting-started/introduction/)


