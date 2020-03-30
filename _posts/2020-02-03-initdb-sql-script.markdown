---
layout: post
title:  "Database Initialisation in Docker"
date:   2020-02-03 07:22:36 +0200
---

Any sql script copied to docker-entrypoint-initdb.d catalog in the mysql container is executed.
This way you can populate your database with some initial data.
What I wanted to achieve was being able to set the sql script each time docker-compse build command
is executed. The solution I've come up with is not vaery intuitive and error prone.
But for now it'll do.
I couldn't figure out how to easily pass a script file path to the
docker container through args.

[code][code]

[code]: https://github.com/lukhen/lukhbook/releases/tag/b2
