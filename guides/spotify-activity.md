---
title: adding my spotify activity to my website
created: 2024-12-25T17:47
updated: 2024-12-26T23:53
hide:
  - Graph
  - Explorer
  - Backlinks
---

the other day, i was checking out [nev flynn's site](https://nevflynn.com/) and drew inspiration from his spotify card showing what he was listening to. considering that spotify api is well documented, i figured this would be a easy addition to jgoon.com. unfortunately, it wasn't as easy as expected.
### spotify api
for my website, i want to show what song im currently listening to, so we'll be using the [get currently playing track](https://developer.spotify.com/documentation/web-api/reference/get-the-users-currently-playing-track) endpoint. however, to call this endpoint, we need to authorize our application.
### authorizing
since we'll be calling the spotify api from our server, we'll need to pick an auth flow with a persistent token. the most intuitive flow would be [client credentials](https://developer.spotify.com/documentation/web-api/tutorials/client-credentials-flow), as the docs recommend this flow for "applications running on the backend". however, since [get currently playing track](https://developer.spotify.com/documentation/web-api/reference/get-the-users-currently-playing-track) requires user authorization, we must use the [authorization code flow](https://developer.spotify.com/documentation/web-api/tutorials/code-flow).

![[Pasted image 20241226175910.png | spotify login flow | 500]]

 the [authorization code flow](https://developer.spotify.com/documentation/web-api/tutorials/code-flow) requires you to grant spotify account level access to generate an authorization code, but unfortunately since we need to generate this on the server, we won't be present to perform this auth flow. fortunately, we can perform this auth flow once, to acquire a `refresh_token` that we can use to perpetually refresh from the server. in this flow, you should add the relevant scopes for the endpoints you wish to use.
### acquiring an access token
using the [token endpoint](https://developer.spotify.com/documentation/web-api/tutorials/refreshing-tokens), we were able to obtain a `refresh_token`  from an authorization code (which we obtained from the manual auth flow in the browser). this `refresh_token` can be used to obtain new `access_tokens`. however, the `refresh_token` isn't long-living. calling the token endpoint will occasionally return a new `refresh_token` in the response. 
### persisting our token
anytime we obtain a new `access_token` that also includes a `refresh_token`, we must update our global store that contains our `refresh_token`.

it is easiest to use the secret manager offered by your provider, but you can use whichever service seems convenient to your architecture. some popular options include: hashicorp vault, aws secrets manager, azure key vault, or gcp secret manager. since my server is deployed on vercel, i opted to use the vercel api to directly update environment variables.

![[Pasted image 20241225221510.png | architecture diagram | 500]]
### completing the flow
now that we can consistently authorize and call the spotify api, we can now handle caching. my server is deployed on vercel, which uses lambda under the hood, so parallel lambda invocation could easily cause the spotify api to make redundant calls. here, i chose an arbitrary 5s ttl, but if you wish to update your data at a higher frequency, feel free to choose whatever value feels right for your use case.

**🎉 congrats! 🎉** you have successfully created a workflow that can consistently call the spotify api from your server!