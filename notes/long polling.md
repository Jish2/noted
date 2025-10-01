---
created: 2024-04-25T11:33
updated: 2025-09-30T17:01
---
#system-design 
the backend keeps the connection open until it has something to return.
once returned (http request resolves), the client opens a new request.
### related
[[Polling]], [[server sent events (SSE)]]

[^1]: [Long polling](https://javascript.info/long-polling)
