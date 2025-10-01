---
created: 2024-12-10T13:59
updated: 2025-09-30T16:55
---
#pattern 
### why it the health check endpoint suffixed with "z"?
internal Google pattern, adds "z" to avoid collision with actual application endpoints

[^1]: [docker - Where does the convention of using /healthz for application health checks come from? - Stack Overflow](https://stackoverflow.com/questions/43380939/where-does-the-convention-of-using-healthz-for-application-health-checks-come-f)