# HTTP GET Request (TryHackMe)

## Overview
- HTTP is a stateless protocol
- GET method is used to retrieve data

---

## Practical Analysis

![image alt](https://github.com/vaibhavattree17/Tryhackme-Labs/blob/main/http-get-request/network.png?raw=true)

- Multiple GET requests observed:
  - index.html
  - style.css
  - script.js

---

## Request Details

![Headers](./images/headers.png)

- Status → 200 OK
- Host → httpdemo.local

---

## Response

![Response](./images/response.png)

- HTML content returned

---

## Key Learning
- One webpage triggers multiple requests
- Each resource is loaded separately

---

## Answers
- Host → www.iamlearning.thm
- Scheme → https
