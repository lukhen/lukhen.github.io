+++
title = "list roam files that were not published (grep)"
categories = ["zettel"]
draft = false
+++

grep -r -L --exclude-dir=.git --exclude-dir=gtd "^#+hugo_publishdate: [0-9][0-9][0-9][0-9]-[0-9][0-9]-[0-9][0-9]" .