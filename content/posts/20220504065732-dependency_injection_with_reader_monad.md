+++
title = "Dependency injection with reader monad."
draft = false
+++

1.  Change the signature of a function f: a-&gt;b to f: a-&gt;Reader&lt;x, b&gt;
2.  Change the signatures of all functions that call f (g: c -&gt; d) to c -&gt; Reader&lt;x, d&gt;
3.  Change all failing tests by introducing some fake x.

Example

We have a type:

```typescript
interface Book {
  title: string
  author: string
}
```

a database:

```typescript
const books: Book[] = [
    { title: "Iliad", author: "Homer" },
    { title: "For whom the bell tolls", author: "Ernest Hemingway" },
    { title: "Treasure Island", author: "Robert Louis Stevenson" }
]
```

2 functions, where one is a dependency of the other:

```typescript
// Assumption: book can always be found
const findBookByTitle:
    (title: string) => Book =
    (title) => A.filter<Book>(b => b.title === title)(books)[0]

const bookAuthor:
    (title: string) => string =
    title => findBookByTitle(title).author
```

and some tests:

```typescript
describe("", () => {
    test("", () => {
	expect(findBookByTitle("Iliad").toEqual(books[0])
	expect(bookAuthor("Iliad").toEqual(findBookByTitle("Iliad")(books).author)
    })
})
```

findBookByTitle is coupled with database.
I want to decouple it using the reader functor from fp-ts functional library.

After refactoring:
{% highlight typescript %}
// Assumption: book can always be found
const findBookByTitle:
    (title: string) `> R.Reader<Book[], Book> =
    (title) => books => A.filter<Book>(b => b.title ==` title)(books)[0]
{% endhighlight %}
\#+END_SRC
All functions calling findBookByTitle now also return Reader:

```typescript
const bookAuthor:
    (title: string) => R.Reader<Book[], string> =
    title => pipe(
	findBookByTitle(title),
	R.map(book => book.author)
    )
```

Tests:

```typescript
describe("", () => {
    test("", () => {
	expect(findBookByTitle("Iliad")(books)).toEqual(books[0])
	expect(bookAuthor("Iliad")(books)).toEqual(findBookByTitle("Iliad")(books).author)
    })
})
```

Unfortunately we can't test an instance of Reader for equality because it's a function. We have to call it.
So let's call it with 'books', the thing we wanted our code to be decoupled from. But now it's only needed here,
in a test, so we can move it here.

```typescript
describe("", () => {
    const books: Book[] = [
	{ title: "Iliad", author: "Homer" },
	{ title: "For whom the bell tolls", author: "Ernest Hemingway" },
	{ title: "Treasure Island", author: "Robert Louis Stevenson" }
    ]

    test("", () => {
	expect(findBookByTitle("Iliad")(books)).toEqual(books[0])
	expect(bookAuthor("Iliad")(books)).toEqual(findBookByTitle("Iliad")(books).author)
    })
})
```