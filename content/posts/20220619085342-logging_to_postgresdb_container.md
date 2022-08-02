+++
title = "logging to postgresdb container"
categories = ["zettel"]
draft = false
+++

docker exec -ti lukhbook-postgresdb-1 /bin/sh
psql -U username -d dbname