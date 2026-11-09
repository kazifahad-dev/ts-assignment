What Is Type Narrowing in TypeScript?
Introduction
TypeScript allows a variable to hold more than one possible type through union types. However, an operation that is safe for a string may not be safe for a number or another object. Type narrowing is the process of checking a value and reducing its possible types before using it. It helps developers write safer code without relying on unsafe assumptions.
Detailed Explanation
The typeof operator is useful for primitive values. For example, a function that accepts string | number can check the value before performing a type-specific operation:
function formatValue(value: string | number): string {
  if (typeof value === "string") {
    return value.trim().toLowerCase();
  }

  return value.toFixed(2);
}
Inside the first branch, TypeScript knows that value is a string. In the remaining branch, it knows that the value is a number.

The instanceof operator narrows values by checking their class or constructor. It is useful when working with objects such as Date:
function describeDate(value: Date | string): string {
  if (value instanceof Date) {
    return value.toDateString();
  }

  return value.toUpperCase();
}
The in operator checks whether an object contains a property. This is helpful when two object types have different fields:
type Admin = { name: string; permissions: string[] };
type Customer = { name: string; purchaseCount: number };

function describeUser(user: Admin | Customer): string {
  if ("permissions" in user) {
    return `Admin: ${user.permissions.length} permissions`;
  }

  return `Customer: ${user.purchaseCount} purchases`;
}
Each check gives TypeScript evidence about the current value, allowing it to offer accurate autocomplete and catch invalid operations during development.
Conclusion
Type narrowing makes union types practical and safe. Use typeof for primitive types, instanceof for class instances, and in for checking object properties. These checks improve reliability while keeping code readable.