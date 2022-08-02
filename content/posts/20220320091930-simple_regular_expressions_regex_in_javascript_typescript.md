+++
title = "Simple regular expressions (regex) in javascript/typescript"
categories = ["zettel"]
draft = false
+++

import \* as String from "fp-ts/lib/string"
const regex = _t\w{2}e_
const origString = 'Now is the time, this is the tame'
String.replace(regex, "place")(origString)

const getUserNameFromUrl : (urlString: string) =&gt; O.Option&lt;string&gt; =
    urlString =&gt; pipe(
	O.tryCatch(() =&gt; new URL(urlString)),
	O.map(url =&gt; url.pathname),
	O.map(pathname =&gt; pathname.match("^/users/.\*$")),
	O.chain(matches =&gt; O.fromNullable(matches)),
	O.map(matches =&gt; matches[0]),
	O.map(pathname =&gt; pathname.split("/")),
	O.chain(A.last)
    )