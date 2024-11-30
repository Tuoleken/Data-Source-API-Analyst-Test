## Enhanced API Request Setup

### How to Use

#### Clone the Repository
```
git clone https://github.com/Tuoleken/Data-Source-API-Analyst-Test.git
```
### Navigate to the Project Directory
```
cd Data-Source-API-Analyst-Test
```
### Import Postman Collection
1. Locate the file `GitHub API Test.postman_collection.json` in the `/Content` folder.
2. Open Postman and go to **Collections > Import**, then select the collection.

### Configure Postman Environment
1. In Postman, navigate to **Environments > Create environment**.
2. Create a new environment named `GitHub`.

2.1. Add a new variable for your GitHub username:
   - **Key**: `github_username`
   - **Value**: Your GitHub username (e.g., `myusername`).

2.2. Add another variable for your GitHub password or personal access token:
   - **Key**: `github_password`
   - **Value**: Your GitHub password or token.

2.3. Click Save the environment and activate it.

### Test API Endpoints
1. Open the imported Postman collection.
2. Select a request and click **Send**.

