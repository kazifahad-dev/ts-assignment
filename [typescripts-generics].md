How Do Generics Work in TypeScript?
Introduction
Generics let developers write reusable functions, interfaces, and classes while preserving information about the types they receive. Instead of using any, a generic function can work with different data types and still provide compile-time type checking. The type parameter acts like a placeholder that TypeScript replaces with the actual type when the function is used.
Detailed Explanation
Consider a function that returns the first item from an array. Without generics, separate functions might be needed for strings and numbers. A generic version handles both:
function getFirst<T>(items: T[]): T | undefined {
  return items[0];
}

const firstName = getFirst<string>(["Mina", "Rafi"]);
const firstScore = getFirst<number>([90, 85]);
TypeScript can often infer T, so explicitly writing <string> or <number> is optional. The return type remains connected to the input type: a string array produces a string result, while a number array produces a number result.

Generics are also important for asynchronous code. A Promise represents a value that may become available later. Promise<T> describes the type of the value produced when that Promise is fulfilled:
async function getUserName(): Promise<string> {
  return "Sadia";
}

async function getUserId(): Promise<number> {
  return 42;
}
The generic type makes the resolved value predictable. When calling getUserName, TypeScript understands that await getUserName() produces a string. This helps prevent mistakes when processing API responses or passing asynchronous results to other functions.

Generics can also use constraints. For example, K extends keyof T limits a key to properties that actually exist on object type T. This makes property-access utilities safer.
Conclusion
Generics combine reusability with strong type safety. They are useful for collections, utility functions, API responses, and Promises because they preserve the relationship between input and output types.