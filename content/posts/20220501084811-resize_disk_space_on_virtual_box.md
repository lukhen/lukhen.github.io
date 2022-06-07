+++
title = "resize disk space on virtual box"
categories = ["zettel"]
draft = false
+++

-   resize disk space:
    -   Plik/Menadżer nośników wirtualnych

-   resize vm arch partition with gparted livecd
    -   Ustawienia/Pamięć/Dodaj napę wirtualny/Gparted
    -   boot

-   increase /tmp space
    mount -o remount,size=5G,noatime /tmp
