---
layout: post
title:  "Decoupling database responsibility in flask"
date:   2020-02-17 12:26:36 +0200
---

I can't accept handling database responsibilities (like retrieving data) in request handlers. I struggled to decoupling it somehow. I'm not sure if this design solution withstands, but for now it seems ok.


[code][code]

[code2]: https://github.com/lukhen/lukhbook/releases/tag/b5
[code]: https://github.com/lukhen/lukhbook/commit/28fa1d8e40a24f53181f5d472c15aafc9e4b4cca

