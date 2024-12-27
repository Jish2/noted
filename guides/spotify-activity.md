---
title: adding my spotify activity to my website
created: 2024-12-25T17:47
updated: 2024-12-26T18:24
---

the other day, i was checking out [nev flynn's site](https://nevflynn.com/)and drew inspiration from his spotify card showing what he was listening to. considering spotify api is well documented, i figured this would be a easy addition. unfortunately, it wasn't as easy as expected.
### spotify api
for my website, i want to show what song im currently listening to, so we'll be using the [get currently playing track](https://developer.spotify.com/documentation/web-api/reference/get-the-users-currently-playing-track) endpoint.
### authorizing
since we'll be calling the spotify api from the server, we'll need to pick an auth flow with a persistent token. the most obvious flow would be [client credentials](https://developer.spotify.com/documentation/web-api/tutorials/client-credentials-flow), as the docs recommend this flow for "applications running on the backend". however, since [get currently playing track](https://developer.spotify.com/documentation/web-api/reference/get-the-users-currently-playing-track) requires user authorization, we must use the [authorization code flow](https://developer.spotify.com/documentation/web-api/tutorials/code-flow).

![[Pasted image 20241226175910.png]]
 
 the [authorization code flow](https://developer.spotify.com/documentation/web-api/tutorials/code-flow) requires you to grant spotify account level access to generate an authorization code, but unfortunately since we need to generate this on the server, we won't be present to perform this auth flow. fortunately, 

![[Pasted image 20241225221510.png]]