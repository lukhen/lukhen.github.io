---
layout: post
title:  "Reading Environment Variables in React"
date:   2020-02-11 11:56:36 +0200
---

It took me at least 10 hours to figure out that I was referencing the api to localhost
instead of the actual ip address it resides in. Funny thing is that the browser kept
returning the CORS problem, and I was digging in the wrong direction.

Making the react app properly read environment varibles is quite tricky as well.
We must not forget thet the react app is  run by the browser on the user's machine
so it doesn't have any env variables. The variables are only built into the app
during the build step.

[code][code]

[code2]: https://github.com/lukhen/lukhbook/releases/tag/b3
[code]: https://github.com/lukhen/lukhbook/commit/d8a5d0f1c656c4a3aa2288c36f09b62832148b62
