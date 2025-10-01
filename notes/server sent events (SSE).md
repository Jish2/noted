---
created: 2023-12-24T12:43
updated: 2025-09-30T17:01
---
#system-design 
**Unidirectional** communication with server and web client

HTTP 1.1

1. request is sent, opening connection with backend
2. backend leaves connections open and continues streaming data to client
    - until connection is closed

## client api's
- EventSource API
- EventSource for Swift