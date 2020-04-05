---
layout: post
title:  "Integration tests distrust"
date:   2020-02-27 12:26:36 +0200
---
I noticed a bug in walking skeleton test - it passes when backend api is not working at all.
I kind of fixed it, but had to use sleep tool to wait for all services to start.
What I realized during this task, is that the usefullness of e2e tests and other integration tests
is rather questionable.
...
contracts
mocks
tdd

[code][code]

[code2]: https://github.com/lukhen/lukhbook/releases/tag/b4
[code]: https://github.com/lukhen/lukhbook/commit/d70a3087f41f7dccdaad5da611685f44e7b215b9