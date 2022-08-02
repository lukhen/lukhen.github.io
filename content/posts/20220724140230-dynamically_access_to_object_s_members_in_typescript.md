+++
title = "dynamically access to object's members in typescript"
categories = ["zettel"]
draft = false
+++

type ObjectKey = keyof typeof obj
const key = "name" as ObjectKey
obj[key]