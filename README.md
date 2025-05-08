## What is the difference between interface and type in TypeScript?
Ans: In TypeScript, we use interface and type to say what shape an object should have like what properties and types it includes.

Both the method work almost the same and below are some simple examples

interface User {
  name: string;
  age: number;
}

type User = {
  name: string;
  age: number;
}

But here are a few small but important differences:

1. interface can be used multiple times like you can write the same interface again and add more properties.

interface User {
  name: string;
}

interface User {
  age: number;
}

But you can’t do this with type. If we try to declare the same type name more than once, it will give an error.

Also type is more flexible with type, we can do more things, like:

type ID = string | number; // union type
type Point = [number, number]; // tuple

----------------------------

## What is keyof in TypeScript?
Ans: TypeScript keyof is a keyword that gives all the keys (property names) of an object as a union of strings for example

type User = {
  name: string;
  age: number;
};

type UserKeys = keyof User; // "name" | "age"
This is useful when we want to work only with the keys of a type:

function getValue(obj: User, key: keyof User) {
  return obj[key]; // Type-safe
}
It stops from using wrong keys like obj['random']
