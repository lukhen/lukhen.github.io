+++
title = "new haskell project in lukhemacs"
categories = ["zettel"]
draft = false
+++

run: git clone git@github.com:lukhen/haskbase.git
remove .git
git init (optionally)
change haskbase with your own name

-   I use projectile grep
-   change haskbase occurances and the haskbase.cabal file name

run tests: cabal test
run app: cabal run newname

Adding new test file:

1.  create file: xxxSpec.hs in test folder

2.  add tests
    module xxxSpec (spec) where
    import Test.Hspec

    spec :: Spec
    spec = do
       describe " xxx " $ do
         it "xxxx" $ do
           "\t  foo bar\n" \`shouldBe\` "foo bar"

<!--listend-->

1.  add module name (xxxSpec) to the spec/other-modules section

run gen hie
probably after every file creation