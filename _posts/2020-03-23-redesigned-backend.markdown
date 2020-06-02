---
layout: post
title:  "Redesigned the backend app"
date:   2020-03-23 07:22:36 +0200
---

Now the request handling behaviors (api endpoints) are encapsulated in their own class.
I prefer this solution because the dependency injection is explicit ( through the constructor)
which, for me at least, makes the code clearer and more testable.
I'm not sure how it's going to work later, when the code becomes more complex. But for now it looks
promising.

[code][code]

[code]: https://github.com/lukhen/lukhbook/commit/e39a5a96a6a6451083c518231ab8dc8d28d90995