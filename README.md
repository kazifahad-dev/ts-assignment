TypeScript Assignment
This repository contains TypeScript solutions for Problems 1–8 and two technical blog posts.
Files
- solutions.ts — implementations of the eight supplied TypeScript problems.
- [`type-narrowing.md`](./type-narrowing.md) — explains narrowing with typeof, instanceof, and in.
- [`typescript-generics.md`](./typescript-generics.md) — explains generics and Promise<T>.
Run locally
1. Install Node.js.
2. Install TypeScript: npm install --save-dev typescript
3. Compile the solution: npx tsc solutions.ts --target ES2020 --strict
The assignment brief also names getUniqueNumbers, Product, and updateProductPrice, but their problem descriptions and expected behavior were not included in the supplied questions. They are intentionally not invented here. Add their specifications before submitting the final version.