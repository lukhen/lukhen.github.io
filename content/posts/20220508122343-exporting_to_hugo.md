+++
title = "exporting to hugo"
publishDate = 2022-05-08
categories = ["zettel"]
draft = false
+++

export zettel:

-   add #+hugo_base_dir: ~/Desktop/blog (it's not neccessary if it's set in .dir-locals.el)
-   if the blog post concerns a project add project-tag in #+filetags section
-   add @zettels category in #+filetags section
-   add publish date in hugo_publishdate section
-   C-c C-e H A

export note

-   if the exported note concerns an itproject
    -   add project-tag in filetags section
-   add @notes category in filetags section
-   add publish date in hugo_publishdate section
-   C-c C-e H A

ignoring certain tags:
<https://www.reddit.com/r/orgmode/comments/8166p9/can_orgexport_or_oxhugo_ignore_some_tags/>

exclude files from exporting:

-   add private tag in hugo_tags section