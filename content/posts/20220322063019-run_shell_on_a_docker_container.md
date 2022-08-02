+++
title = "Run shell on a docker container"
publishDate = 2022-03-22
categories = ["zettel"]
draft = false
+++

docker exec -ti container-name /bin/sh or /bin/bash

//
docker run --interactive --tty --entrypoint /bin/sh container-namei