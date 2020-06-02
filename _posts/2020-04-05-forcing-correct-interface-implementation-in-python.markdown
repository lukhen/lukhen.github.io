---
layout: post
title:  "Forcing correct interface implementation in python."
date:   2020-04-05 11:49:36 +0200
---


It's such an annoying bug [made it here][bug] [fixed here][fix]. It happens when you follow mockist approach to tdd, design by contract approach and yagni rule and you are too lazy to use any kind of a mechanism that would force interface implementation. It's very risky. Changing a signature of a method in the code will be unnoticed by tests. They will pass, and the bug will be exposed only in the runtime. It could also be caught in the integrated/e2e tests, but I rather not use them in the process of construction.

In python there are a few possibilities to address that. I tried zope.interface but it doesn't work well for me, because it's problematic to build mocks with interface as a spec. Builtin abstract classes work quite good. You can easily use them as a spec in mocks. But they don't force the interface implementation correctly. It's enough for the implementer to have a member with the same name. It doesn't even have to  be a method (python 3.8). I ended up with a solution, that works for me [here][solution]. I noticed though that dynamically created classes are not the same as those created statically. I'll be testing this solution... 

[bug]: https://github.com/lukhen/lukhbook/commit/ab72e388208c20e5bca796991e062c74c3fa765c
[fix]: https://github.com/lukhen/lukhbook/commit/aa37049b546fd6bbeecddde3c68a832d55823aec
[solution]: https://github.com/lukhen/lukhbook/commit/5894e7d33ddb8c6653ac99c864a9e3959fdab238