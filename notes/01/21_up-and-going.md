# Notes - YDKJS: Up & Going

January 21 (Sunday)

---

It's mostly a glossary of terms, but I noted other things as well. Here goes:

* **Statement.** group of symbols/literals and operators that perform a specific
  task
* **Expression.** group of symbols and such that evaluate to a value
* **Interpreting.** reading source code as it is and executing it
* **Compiling.** transforming the source code into a lower-level version in
  advance; that lower-level code is then executed
* **Operators.** used to do something to a value (e.g., adding two numbers)
* **Literals.** values that are _literally_ written in the source code
* **Coercion.** converting a value of a particular type to a different type
* **Type.** classification of data; determines what sorts of operations can be
  done on a value
* **Comments.** parts of code that the compiler/interpreter ignores
  * code without comments is suboptimal
  * too many comments can be a sign of poor code
  * comments should explain why, not what, How too, if need be
  * (my own interpretation) comments can be used to make the structure of the
    code clearer (i.e., they can be used to group together code that do similar
    things)
* **Variable.** symbolic container for a value; their primary purpose is to
  manage program state
* **Static typing.** type is bound to the variable (i.e., a variable of a
  certain type can only contain data of the same type)
* **Dynamic typing.** type is bound to the value (i.e., a variable can holl all
  sorts of data regardless of type); JS is dynamically typed
* **Constant.** variable whose value cannot change (isn't calling them variables
  an oxymoron?)
* **Block.** group of statements, grouped by braces
* **Conditional.** control structure that executes a block of code depending on
  whether its condition is satisfied or not
* **Loop.** control structure that executes a block of code repeatedly as long
  as its condition is satisfied
* **Function.** named section of code that can be called. Can be useful for code
  that needs to be used multiple times, as well as simply for organizing code,
  even if that function is only called once
* **(Lexical) Scope.** collection of variables and rules on how to access them.
  Code in one inner scope can access variables from the outer scope that
  contains it.
* **JS Types:**
  * string
  * number
  * boolean
  * null
  * undefined
  * object
  * symbol (ES6)
* **typeof.** operator that produces the type of a value. Possible values:
  * `'string'`
  * `'number'`
  * `'boolean'`
  * `'undefined'`
  * `'object'`
  * `'function'`
  * `'symbol'`
  * `typeof null` produces `'object'`!
* **Object.** compound data that can hold multiple other values
* **Property.** named value in an object; can be accessed with dot notation or
  bracket notation
* **Dot notation.** `obj.a`; easier to read; use whenever possible
* **Bracket notation.** `obj['a']`; used when a property contains special
  characters (like spaces or punctuation); can also be used for accessing
  property names stored in variables
* **Array.** specialized object where values are stored in numerically indexed
  positions; `typeof [] == 'object'`
* **Functions** are also specialized objects, so they can also contain
  properties like regular objects (in fact a certain special function does!)
* When a built-in method is used on a primitive, the primitive is automatically
  **boxed** in its native wrapper object. Primitive values don't have methods
  in them; the wrappers do.
* **Explicit coercion.** coercion you can see from the code
* **Implicit coercion.** coercion as a result of some side-effect of an
  operation (e.g., when comparing a string against a number, implicit coercion
  takes place; the string is coerced to a number)
* **Falsy values.** values that (aside from the value `false`) when coerced to
  boolean, becomes `false`:
  * `''` (the empty string)
  * `0`, `-0`, and `NaN`
  * `null`, `undefined`
  * `false`
  * The rest are truthy!
* **`==`** checks for equality while allowing coercion
* **`===`** checks for equality without allowing coercion
* Avoid `==` when
  * either side of the comparison is boolean
  * either side is `''`, `0` (perhaps `-0` too), or `[]`
* **`!=`** and **`!==`** produce the inverse of their counterparts
* When comparing two reference types, both `==` and `===` will return `true`
  **if and only if both sides are a reference to the same value.**
* `a < b` will compare lexicographically if both sides are strings
  * if one or both is not a string, both are coerced to numbers
* Variable names (**identifiers**) must start with a letter, `$`, or `_`.
  Subsequent characters can be a number
* **Reserved words** (`if`, `null`, etc.) can't be used as variable names but
  can be used as object property names
* **Hoisting.** a variable declaration is "moved" at the top of its enclosing
  scope; this makes the variable accessible to the entire scope it's in, even by
  code that's written above the actual variable declaration
  - **Avoid hoisting variables**. Hoisting functions are okay.
* **Strict mode** disables auto-global variables (variables that are not
  formally declared with the `var` keyword), among other things
* **Functions themselves are values.** You can pass them around in your code
  like you do with regular objects
* **IIFE.** immediately-invoked function expression; functions that are executed
  as soon as they are defined
* **Closure.** a way to "remember" the variables in a function's scope even
  after the function has finished running
* **Module.** a construct that hides private implementation details and exposes
  a public interface so other code can interact with its innards; a common
  application of closures.
* **`this`.** a reference to some object; the object it refers to depends on how
  the function where it appears is called
* **Prototype.** object that's "linked" to another object. If an object doesn't
  have some property, it will look up its prototype to see if it has it
* **Polyfilling.** implementing a new feature in such a way it can run in
  environments that don't officially support it
* **Transpiling.** converting code with new syntax into an equivalent verion
  that uses older syntax
* Why transpile?
  * Newer syntax is generally more readable than their older syntax equivalent
  * Newer syntax can be optimized by modern browsers, while we can continue to
    serve the older syntax equivalent to older browsers
  * Using newer syntax is like a beta test for the people writing the specs.
    They get to have feedback and change things if necessary before they become
    permanent
* **Non-JS JS.** the global `document` object in browsers is a host object and
  isn't part of the JS spec. Same with `alert` and `console.log`.
* About the rest of the books,
  * **Scope & Closures** discusses function scopes, closures, and the module
    pattern as an application of closures.
  * **this & Object Prototypes** discusses the `this` keyword, how its binding
    is determined, the prototype mechanism, how it's different from traditional
    OOP, and how it's used to delegate behavior.
  * **Types & Grammar** discusses type coercion, how coercion can be used to
    your advantage, and misconceptions about coercion.
  * **Async & Performance** discusses how asynchrony is a major part of
    programming JS applications, techniques for writing async code, callbacks
    and the problem with them, promises and generators ad better tools for
    dealing with asynchrony, and other topics about overall performance.
  * **ES6 & Beyond** discusses the wide range of ES6 features and the rapid
    evolution of the language.

There's already this much notes about the first book. Notes about the next ones
will be much longer!
