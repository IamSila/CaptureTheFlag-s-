# IDOR
## intresting features and parameters
- customer feedback: http://10.6.6.12:3000/#/contact   [IDOR PRESENT]
- customer complaint: http://10.6.6.12:3000/#/complain     -> [IDOR PRESENT]
- /rest/chatbot/respond -> try switching the token as the response tries to process it

```
    HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
X-Content-Type-Options: nosniff
X-Frame-Options: SAMEORIGIN
Feature-Policy: payment 'self'
X-Recruiting: /#/jobs
Content-Type: application/json; charset=utf-8
Content-Length: 845
ETag: W/"34d-otfQoyr/rfzx+0AKp2qT6bkN0BU"
Vary: Accept-Encoding
Date: Fri, 06 Mar 2026 20:11:52 GMT
Connection: keep-alive
Keep-Alive: timeout=5

{"action":"response",
"body":"Nice to meet you You can call me cii, I'm Juicy",
"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJzdGF0dXMiOiJzdWNjZXNzIiwiZGF0YSI6eyJpZCI6MjMsInVzZXJuYW1lIjoiWW91IGNhbiBjYWxsIG1lIGNpaSIsImVtYWlsIjoiY2lpeDBoNGNrM3JAZ21haWwuY29tIiwicGFzc3dvcmQiOiJlZjdkZWYzMjAwYzNmZmM0ZGRjYjMyYTEyZjVlNjRhZCIsInJvbGUiOiJjdXN0b21lciIsImRlbHV4ZVRva2VuIjoiIiwibGFzdExvZ2luSXAiOiIwLjAuMC4wIiwicHJvZmlsZUltYWdlIjoiL2Fzc2V0cy9wdWJsaWMvaW1hZ2VzL3VwbG9hZHMvZGVmYXVsdC5zdmciLCJ0b3RwU2VjcmV0IjoiIiwiaXNBY3RpdmUiOnRydWUsImNyZWF0ZWRBdCI6IjIwMjYtMDMtMDZUMjA6MDY6MjIuNDEyWiIsInVwZGF0ZWRBdCI6IjIwMjYtMDMtMDZUMjA6MTE6NTIuODczWiIsImRlbGV0ZWRBdCI6bnVsbH0sImlhdCI6MTc3MjgyNzkxM30.x3EzeIiQKZu-4SDJoF-0LOv7C8npsxjH-61m1rEQnk_VmHWEy916eAeeAj6ywig9Qm8I66JvXQ3kbucmiyXzjIEkEJWygY2SIvk3d1srzlysMJfhhzDJR6y8rbpmQs8aRqTIOVoVmeW8MXCm53YSXX4L9p1Ql_okJTBu0wCdsjU"}



```


- /api/feedback -> Exposes all users.
- /rest/memories -> Exposes more users.

- /rest/chatbot/respond -> if I change the token, can I interact with the support chat as another user

- /rest/products/1/reviews -> Can I add a review using another user's email? [IDOR PRESENT]

- /rest/track-order/b827-d4e01690bb71282e -> we can track another user's order by changing the order-id [IDOR PRESENT]

- /change-password -> I am able to change password if I remove the current password parameter. If I change the token to another user's password can I change that user's password?


