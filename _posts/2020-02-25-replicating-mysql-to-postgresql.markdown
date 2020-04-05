---
layout: post
title:  "Replicating mysql to postgres"
date:   2020-02-25 11:40:36 +0200
---
Running pg_chameleon replication system within docker container.
I've complicated my system a bit. Instead of using the main mysql database,
I've set replication mechanism. Now I can switch to postgres db.
I did this because of one reason - mysql db is used by other, third-party,
closed-source programme, which I prefer not to mess up with, at least for now.

Setting pg-chameleon had seemed quite easy, but it ended up being tricky, especially
to make it running within docker container.
Documentation is clear, and it's easy to start the replication, as long as you only
need a static configuration file. I decided to set config variables based on environment
variables from docker-compose file. That made me dig into creating yaml file using configuration
script. 

[code][code]

[code2]: https://github.com/lukhen/lukhbook/releases/tag/b7
[code]: https://github.com/lukhen/lukhbook/commit/d7c73e6400507483ed3e0d0403e310c80066cdf8
