---
updated: 2025-10-06T21:29
created: 2025-10-06T21:08
---
#infra/auth 
proof key for code exchange (pixie)

secure auth for apps without the ability to store secrets (backendless clients) 

### why
when authorizing clients, we cannot securely store secrets. any client could replicate the oauth flow and gain a token for our app. this is what pkce prevents.

if the flow is intercepted at the auth server step, there is no way of mocking here (since we don't know the client original secret, only the hash)

### how
we generate some secret and hash it, which is exchanged for a code on the auth server associated with that hash. the client can exchange that code with the secret (prehash) for an access token.

the auth server will hash the secret, and cross reference it with the hash you gave it in the original exchange for the code to verify that you are the same requester. 

### steps
1. create secret string
2. hash secret string
3. redirect to auth server, sending hash
4. user completes oauth flow
5. auth server redirects to app, with a code
6. app exchanges code and original secret for tokens


```mermaid
sequenceDiagram
    participant C as Client Application
    participant AS as Authorization Server
    participant RS as Resource Server

    C->>C: 1. Generate code_verifier (random string)
    C->>C: 2. Generate code_challenge (S256 hash of code_verifier)

    C->>AS: 3. Redirect with Authorization Request (code_challenge, code_challenge_method=S256, client_id, redirect_uri, scope, response_type=code)
    AS->>AS: 4. Authenticate User & Obtain Consent
    AS-->>C: 5. Redirect with Authorization Code (code)

    C->>AS: 6. Token Request (code, code_verifier, client_id, redirect_uri, grant_type=authorization_code)
    AS->>AS: 7. Verify code_challenge_method (S256)
    AS->>AS: 8. Verify code_verifier against stored code_challenge
    AS-->>C: 9. Respond with Access Token & ID Token (optional)

    C->>RS: 10. API Request with Access Token
    RS->>RS: 11. Validate Access Token
    RS-->>C: 12. Respond with Protected Resource
```

[^1]: [OAuth is Broken Without This \| Meet PKCE - YouTube](https://www.youtube.com/watch?v=5FrA0UzV1Aw)
[^2]: [PKCE for OAuth 2.0](https://oauth.net/2/pkce/)