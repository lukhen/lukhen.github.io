+++
title = "Type classes in functional programming"
categories = ["zettel"]
draft = false
+++

Type class:

-   set of functions specs (signatures) or constant names

A type can belong to a type class.
A programmer can make any type A belong to a type class by using an instance declaration that
defines implementations of all type class' members for the particular type A.

For example:
We have a type class Eq:

```typescript
interface  Eq<A>{
    equals: (a: A, b: A) => boolean
  }
```

Let's make 'number' type belong to Eq type class.
We declare an instance of Eq type class by implementing all members for 'number' type.

```typescript
const eqNumber: Eq<number> = {
  equals: (a, b) => a === b
}
```

Functor is a type class.
To declare an instance of Functor type class in typescript/fp-ts we need some extra hacks:

For Array:

```typescript
export const AURI = "Array"
export type AURI = typeof AURI
export const functorArray: Functor1<AURI> = {
    URI: AURI,
    map: (fa, f) => fa.map(f)
}
```

or for an own type:

```typescript
export interface Resp<A> {
    url: string
    status: number
    headers: Record<string, string>
    body: A
}
export const URI = 'Resp'

export type URI = typeof URI

declare module 'fp-ts/HKT' {
    interface URItoKind<A> {
	Resp: Resp<A>
    }
}
function map<A, B>(fa: Resp<A>, f: (a: A) => B): Resp<B> {
    return { ...fa, body: f(fa.body) }
}

export const functorResp: Functor1<URI> = {
    URI,
    map
}
```

Type class instances are useful in combinators.

<https://github.com/gcanti/fp-ts/discussions/1724>
<https://bartoszmilewski.com/2014/01/14/functors-are-containers/>