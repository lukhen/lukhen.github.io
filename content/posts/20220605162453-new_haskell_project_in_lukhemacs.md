+++
title = "new haskell project in lukhemacs"
categories = ["zettel"]
draft = false
+++

Haskell config:

-   install ghcup with with hls ([here](https://www.haskell.org/ghcup/)):
    curl --proto '=https' --tlsv1.2 -sSf <https://get-ghcup.haskell.org> | sh

-   mkdir project
-   cabal init  [cabal docs and simple tut](https://cabal.readthedocs.io/en/3.6/getting-started.html)
-   cabal install implicit-hie
-   gen-hie &gt; hie.yaml (to make lsp-haskell work)