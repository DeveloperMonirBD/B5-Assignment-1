## Understanding Key TypeScript Concepts
TypeScript is a powerful language that adds static typing to JavaScript, making code more maintainable and robust. In this blog post, we’ll explore two essential concepts:

1. The keyof Keyword in TypeScript
2. Using Union and Intersection Types

### 1. Understanding keyof in TypeScript
The "keyof" keyword is used to extract the keys of an object type as a union of string literals. This is especially useful when working with type-safe functions that rely on object properties dynamically.

### Example:

type User = {
  id: number;
  name: string;
  email: string;
};

function getUserProperty<T, K extends keyof T>(user: T, key: K): T[K] {
  return user[key];
}

const user: User = { id: 1, name: "Md.", email: "md@example.com" };

console.log(getUserProperty(user, "name")); // Output: Md.
console.log(getUserProperty(user, "email")); // Output: md@example.com

## Why is keyof useful?
-   Ensures type safety when accessing object properties.
-   Reduces errors caused by incorrect property names.
-   Helps build reusable, dynamic utility functions.

## 2. Using Union and Intersection Types
Union and intersection types allow flexible type composition, making TypeScript more expressive.

### Union Types
Union types enable a variable to hold multiple types.
type Status = "success" | "error" | "loading";

function displayStatus(status: Status) {
  console.log(`Current status: ${status}`);
}

displayStatus("success"); // ✅ Valid
displayStatus("error"); // ✅ Valid

### Intersection Types
Intersection types combine multiple types into one.

type PersonalInfo = {
  name: string;
  age: number;
};

type ContactInfo = {
  email: string;
  phone: string;
};

type UserProfile = PersonalInfo & ContactInfo;

const profile: UserProfile = {
  name: "Md.",
  age: 25,
  email: "md@example.com",
  phone: "123-456-7890",
};

console.log(profile);

### Why are union and intersection types useful?
-   Unions enhance flexibility when defining multiple possible values.
-   Intersections allow creating more structured and reusable object types.

## What to Submit
-   Public Github Repo Link : https://github.com/DeveloperMonirBD/B5-Assignment-1