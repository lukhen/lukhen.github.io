+++
title = "pushing and pulling to github"
categories = ["zettel"]
draft = false
+++

_wrong_ each repo has to have its own ssh key
repo ssh keys are used in advanced configurations
it's enough to set profile ssh key, ssh-add the key

sometimes it's neccessary to flush key-ring
ssh-add -D

pushing
ssh-add ~/Desktop/droplet1_rsa
magit push

pulling
on remote:
eval \`ssh-agent -s\`
ssh-add ~/.ssh/github
git pull