---
updated: 2025-09-30T19:16
created: 2025-09-30T19:08
---
#meta/moc #system-design 

methods for clients to listen backend

## why
traditionally, a backend can only listen to a frontend
- realtime elements cannot be updated

## methods
- [[server sent events (SSE)]]
- [[Websockets]]
- [[Polling]]
- [[pubsub]]???

## choice [^fn1]
![[Pasted image 20240104154836.png]]

## references
[^fn1]: [Don't Use Websockets by Code with Ryan](https://www.youtube.com/watch?v=6QnTNKOJk5A)
