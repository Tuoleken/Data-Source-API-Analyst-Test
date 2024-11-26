# **API Documentation**

This document provides an overview of the GitHub API endpoints used for this project, including details about request parameters, expected responses, and error handling strategies.

---

## **1. Search Repositories**

**Endpoint:**  
`GET /search/repositories`

**Description:**  
Search for public repositories on GitHub using a query.

**Required Headers:**  
- `Accept: application/vnd.github+json`

**Query Parameters:**  
- `q` *(string)*: The search keywords.  
- `sort` *(optional, string)*: The sort field. Can be `stars`, `forks`, or `updated`. Default: best match.  
- `order` *(optional, string)*: The order of results. Can be `asc` or `desc`. Default: `desc`.  

**Example Request:**  
```http
GET https://api.github.com/search/repositories?q=python&sort=stars&order=desc

```
## **Example Response (200 OK)**

```json
{
  "total_count": 12345,
  "incomplete_results": false,
  "items": [
    {
      "id": 1,
      "name": "example-repo",
      "owner": {
        "login": "example-user"
      },
      "stargazers_count": 1000,
      "forks_count": 100
    }
  ]
}
```
## 2. List Repository Commits

**Endpoint:**  
`GET /repos/{owner}/{repo}/commits`

**Description:**  
Retrieve a list of commits from a specified repository.

**Required Headers:**  
- `Accept: application/vnd.github+json`

**Path Parameters:**  
- `owner` *(string)*: The username of the repository owner.  
- `repo` *(string)*: The name of the repository.

**Query Parameters:**  
- `sha` *(optional, string)*: The branch or commit SHA to filter. Default: default branch.  
- `per_page` *(optional, integer)*: Results per page. Default: 30.  
- `page` *(optional, integer)*: Page number of results to fetch.

**Example Request:**  
```http
GET https://api.github.com/repos/example-user/example-repo/commits
```
## **Example Response (200 OK)**

```json
[
  {
    "sha": "abc123",
    "commit": {
      "message": "Initial commit",
      "author": {
        "name": "example-user",
        "date": "2024-01-01T00:00:00Z"
      }
    }
  }
]
```

## 3. Get Repository Contents

**Endpoint:**  
`GET /repos/{owner}/{repo}/contents/{path}`

**Description:**  
Retrieve the contents of a file or directory in a repository.

**Required Headers:**  
- `Accept: application/vnd.github+json`

**Path Parameters:**  
- `owner` *(string)*: The username of the repository owner.  
- `repo` *(string)*: The name of the repository.  
- `path` *(string)*: The content path.

**Query Parameters:**  
- `ref` *(optional, string)*: The name of the commit/branch/tag. Default: default branch.

**Example Request:**  
```http
GET https://api.github.com/repos/example-user/example-repo/contents/README.md
```

## **Example Response (200 OK)**

```json
{
  "name": "README.md",
  "path": "README.md",
  "size": 1024,
  "content": "VGhpcyBpcyBhIHNhbXBsZSBSRUFETUUgZmlsZS4=",
  "encoding": "base64"
}
```
