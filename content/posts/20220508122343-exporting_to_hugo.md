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


## preparing a note file for publishing {#preparing-a-note-file-for-publishing}

-   if a note has the possibility to be published in the future: tag with publishable
-   if can be published: tag with journal
-   if should not be published and probably won't be: mark with private
-   if there are any notes to be published: delete line hugo_tags: private

-   add summary and hugo: more
-   add tags: for each itproject, subject it's about: foss, linux, functional_programming, etc


## preparing a zettel file for publishing {#preparing-a-zettel-file-for-publishing}

if it's to be completed: tag with treasure
if it can be published: remove line: hugo_tags: private


## exporting a single file to hugo {#exporting-a-single-file-to-hugo}


## exporting the whole roam to hugo {#exporting-the-whole-roam-to-hugo}

mark all files except .git
C-+
