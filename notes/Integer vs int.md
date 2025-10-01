---
created: 2024-02-23T20:56
updated: 2024-02-23T20:58
---
#language/java

use `int` if you can, if can be `null` or used as an Object e.g. Generics, use `Integer`

- Prefer `int` for performance reasons
- Methods that take objects (including generic types like `List<T>`) will implicitly require the use of `Integer`
- Use of `Integer` is relatively cheap for low values (-128 to

127. because of interning - use `Integer.valueOf(int)` and not new Integer(int)

- Do not use ` ==` or `!=` with Integer types
- Consider using `Integer` when you need to represent the absence of a value (null)
- Beware unboxing Integer values to int with null values