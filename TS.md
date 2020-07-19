
### TS in OOP
https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes-oop.html
- Benefit: better code completion, earlier detection of errors, and clearer communication between parts of your program
- common misconceptions and pitfalls
- In JavaScript, functions can live anywhere, and data can be passed around freely without being inside a pre-defined class or struct. “Free” functions (those not associated with a class) working over data without an implied OOP hierarchy tends to be the preferred model for writing programs in JavaScript.
- Type
  - In TypeScript, it’s better to think of a type as **a set of values** that share something in common.
    - TypeScript’s type system is **structural**, not nominal: 
      - **same structure, same type**
      - if we construct an object that satisfies an interface, we can use that object where that interface is expected even though there was **no declarative** relationship between the two
    - not reified: There’s **no type at runtime**
  - In C# or Java, it’s meaningful to think of a one-to-one correspondence between runtime types and their compile-time declarations.
  
  
### Decorator
https://www.typescriptlang.org/docs/handbook/decorators.html
- A Decorator is a special kind of **declaration** that can be **attached to** a class declaration, method, accessor, property, or parameter. Decorators use the form **@expression**, where expression must **evaluate to a function** that will be called at runtime with information about the decorated declaration.
- Decorator Composition
  - fucntion composition: g(f(x))
  - The expressions for each decorator are evaluated top-to-bottom. 
  - The results are then called as functions from bottom-to-top.
  
  
