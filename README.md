# Coding Standards

## Table of content

- Summary
- Naming Conventions
- Coding Style
- Language Usage
- Arrays
- Classes & Constructors
- Types
- References
- Objects
- Destructuring
- Strings
- Functions
- Variables

---

## Summary

### Naming Conventions

"c"  = camelCase
"P" = PascalCase
"_" = Prefix with _Underscore
"x" = Not Applicable

| Identifier  | Public | Protected | Internal | Private | Notes |
| ----------  | -------|-----------|----------|---------|-------|
| Project File| P      | x         | x        | x       | Match Assembly & Namespace |
| Source File | P      | x         | x        | x       | Match contained class |
| Other Files | P      | x         | x        | x       | Apply where possible |
| Namespace   | P      | x         | x        | x       | Partial Project / Assembly match|
| Class or Struct | P  | P         | P        | P       | Add suffix of subclass |
| Interface   | P      | P         | P        | P       | Prefix with capital I |
| Generic Class [C#v2+] | P | P | P | P | Use T or K as Type identifier|
| Method | P | P | P | P | Use a Verb or Verb-Object pair |
| Property | P | P | P | P | Do not prefix with Get or Set | 
| Field | P | P | P | _c | Only use Private field. No Hungarian Notation! |
| Constant | P | P | P | _c | |
| Static Field | P | P | P | _c | Only use private fields |
| Enum | P | P | P | P | Options are also PascalCase |
| Delegate | P | P | P | P | |
| Event | P | P | P | P | |
| Inline Variable | x | x | x | c | Avoid single-character and enumerated names |
| Parameter | x | x | x | c | |

### Coding Style

| Code | Style |
| ---- | ----- |
| Source Files | One Namespace per file and one class per file |
| Curly Braces | On new line. Always use braces when option |
| Indention | Use tabs with size of 4 |
| Comments | Use // or /// but not /* ... */ and do not flowerbox |
| Variables | One variable per declaration |

### Language Usage

| Code | Style |
| ---- | ----- |
| Native Data Types | Use built-in C# native data types vs .NET CTS types (use int not Int32)|
| Enums | Avoid changing default type |
| Generics | Prefer Generic Types over standard or strong-types classes |
| Properties | Never prefix with Get or Set |
| Methods | Use a maximum of 7 parameters |
| base and this | Use only in constructors or within an override |
| Ternary conditions | Avoid complex conditions |
| foreach statements | Do not modify enumerated items within a foreach statement |
| Conditionals | Avoid evaluating Boolean conditions against true or false. No embedded assignment. Avoid embedded method invocation. |
| Exceptions | Do not use exceptions for flow control. Use throw; not throw e; when re-throwing. Only catch when you can handle. Use validations to avoid exceptions. Derive from Exception not ApplicationException. |
| Events | Always check for null before invoking. |
| Locking | Use lock() not Monitor.Enter(). Do not lock on an object type or "this". Do lock on private objects. |
| Dispose() & Close() | Always invoke them if offered, declare when needed. |
| Finalizers | Avoid. Use the C# Desctructors. Do not create Finalize() method. |
| AssemblyVersion | Increment manually |
| ComVisibleAttribute | Set to false for all assemblies |

---

## Naming  Conventions

Consistency is the key to maintainable code. This statement is most true for naming your projects, source files, and
identifiers including Fields, Variables, Properties, Methods, Parameters, Classes, Interfaces, and Namespaces.

### General Guidelines

1. Always use Camel Case or Pascal Case names.
2. Avoid ALL CAPS and all lowercase names. Single lowercase words or letters are acceptable.
3. Do not create declarations of the same type (namespace, class, method,property, field, or parameter) and access modifier (protected, public, private, internal) that vary only by capitalization.
4. Do not use names that begin with a numeric character.
5. Do add numeric suffixes to identifier names.
6. Always choose meaningful and specific names.
7. Always err on the side of verbosity not terseness.
8. Variables and Properties should describe an entity not the type or size.
9. Do not use Hungarian Notation! Example: strName or iCount
10. Avoid using abbreviations unless the full name is excessive.
11. Avoid abbreviations longer than 5 characters.
12. Any Abbreviations must be widely known and accepted.
13. Use uppercase for two-letter abbreviations, and Pascal Case for longer abbreviations.
14. Do not use C# reserved words as names.
15. Avoid naming conflicts with existing .NET Framework namespaces, or types.
16. Avoid adding redundant or meaningless prefixes and suffixes to identifiers
17. Do not include the parent class name within a property name. Example: Customer.Name NOT Customer.CustomerName
18. Try to prefix Boolean variables and properties with “Can”, “Is” or “Has”.
19. Append computational qualifiers to variable names like Average, Count, Sum, Min, and Max where appropriate.
20. When defining a root namespace, use a Product, Company, or Developer Name as the root.

### Name Usage & Syntax

**Project File**

Pascal Case.
Always match Assembly Name & Root Namespace.

Example:
LanceHunt.Web.csproj -> LanceHunt.Web.dll -> namespace LanceHunt.Web 

[Add more]

## Coding  Style

Coding style causes the most inconsistency and controversy between developers. Each developer has a preference, and
rarely are two the same. However, consistent layout, format, and organization are key to creating maintainable code.
The following sections describe the preferred way to implement C# source code in order to create readable, clear, and
consistent code that is easy to understand and maintain

### Formatting

1. Never declare more than 1 namespace per file.
2. Avoid putting multiple classes in a single file.
3. Always place curly braces ({ and }) on a new line.
4. Always use curly braces ({ and }) in conditional statements.
5. Always use a Tab & Indention size of 4.
6. Declare each variable independently – not in the same statement.
7. Place namespace “using” statements together at the top of file. Group .NET namespaces above custom namespaces.
8. Group internal class implementation by type in the following order: Member variables. Constructors & Finalizers. Nested Enums, Structs, and Classes. Properties. Methods
9. Sequence declarations within type groups based upon access modifier and visibility: Public Protected Internal Private
10. Segregate interface Implementation by using #region statements.
11. Append folder-name to namespace for source files within sub-folders.
12. Recursively indent all code blocks contained within braces.
13. Use white space (CR/LF, Tabs, etc) liberally to separate and organize code.
14. Only declare related attribute declarations on a single line, otherwise stack each attribute as a separate declaration.
15. Place Assembly scope attribute declarations on a separate line.
16. Place Type scope attribute declarations on a separate line.
17. Place Method scope attribute declarations on a separate line.
18. Place Member scope attribute declarations on a separate line.
19. Place Parameter attribute declarations inline with the parameter.
20. If in doubt, always err on the side of clarity and consistency.

### Code Commenting

1. All comments should be written in the same language, be grammatically correct, and contain appropriate punctuation.
2. Use // or /// but never /* … */
3. Do not “flowerbox” comment blocks.
4. Use inline-comments to explain assumptions, known issues, and algorithm insights.
5. Do not use inline-comments to explain obvious code. Well written code is self documenting.
6. Only use comments for bad code to say “fix this code” – otherwise remove, or rewrite the code!
7. Include comments using Task-List keyword flags to allow comment-filtering. 
8. Always apply C# comment-blocks (///) to public, protected, and internal declarations.
9. Only use C# comment-blocks for documenting the API.
10. Always include summary comments. Include param, return, and exception> comment sections where applicable.
11. Include see cref=””/ and seeAlso cref=””/ where possible.
12. Always add CDATA tags to comments containing code and other embedded markup in order to avoid encoding issues.

## Language  Usage

### General

1. Do not omit access modifiers. Explicitly declare all identifiers with the appropriate access modifier instead of allowing the default. 
2. Do not use the default (“1.0.*”) versioning scheme. Increment the AssemblyVersionAttribute value manually.
3. Set the ComVisibleAttribute to false for all assemblies.
4. Only selectively enable the ComVisibleAttribute for individual classes when needed. 
5. Consider factoring classes containing unsafe code blocks into a separate assembly.
6. Avoid mutual references between assemblies. 

### Variable & Types

1. Try to initialize variables where you declare them.
2. Always choose the simplest data type, list, or object required.
3. Always use the built-in C# data type aliases, not the .NET common type system (CTS). 
4. Only declare member variables as private. Use properties to provide access to them with public, protected, or internal access modifiers.
5. Try to use int for any non-fractional numeric values that will fit the int datatype - even variables for nonnegative numbers.
6. Only use long for variables potentially containing values too large for an int.
7. Try to use double for fractional numbers to ensure decimal precision in calculations.
8. Only use float for fractional numbers that will not fit double or decimal.
9. Avoid using float unless you fully understand the implications upon any calculations.
10. Try to use decimal when fractional numbers must be rounded to a fixed precision for calculations. Typically this will involve money.
11. Avoid using sbyte, short, uint, and ulong unless it is for interop (P/Invoke) with native libraries 
12. Avoid specifying the type for an enum - use the default of int unless you have an explicit need for long (very uncommon).
13. Avoid using inline numeric literals (magic numbers). Instead, use a Constant or Enum.
14. Avoid declaring string literals inline. Instead use Resources, Constants, Configuration Files, Registry or other data sources.
15. Declare readonly or static readonly variables instead of constants for complex types.
16. Only declare constants for simple types.
17. Avoid direct casts. Instead, use the “as” operator and check for null.
18. Always prefer C# Generic collection types over standard or strong-typed collections. [C#v2+]
19. Always explicitly initialize arrays of reference types using a for loop.
20. Avoid boxing and unboxing value types. 
21. Floating point values should include at least one digit before the decimal place and one after.
22. Try to use the “@” prefix for string literals instead of escaped strings.
23. Prefer String.Format() or StringBuilder over string concatenation.
24. Never concatenate strings inside a loop.
25. Do not compare strings to String.Empty or “” to check for empty strings. Instead, compare by using String.Length == 0.
26. Avoid hidden string allocations within a loop. Use String.Compare() for case-sensitive

### Flow Control

1. Avoid invoking methods within a conditional expression.
2. Avoid creating recursive methods. Use loops or nested loops instead.
3. Avoid using foreach to iterate over immutable value-type collections. E.g. String arrays.
4. Do not modify enumerated items within a foreach statement.
5. Use the ternary conditional operator only for trivial conditions. Avoid complex or compound ternary operations.
6. Avoid evaluating Boolean conditions against true or false.
7. Avoid assignment within conditional statements.
8. Avoid compound conditional expressions – use Boolean variables to split parts into multiple manageable expressions.
9. Avoid explicit Boolean tests in conditionals.
10. Only use switch/case statements for simple operations with parallel conditional logic.
11. Prefer nested if/else over switch/case for short conditional sequences and complex conditions.
12. Prefer polymorphism over switch/case to encapsulate and delegate complex operations.

### Exceptions

1. Do not use try/catch blocks for flow-control.
2. Only catch exceptions that you can handle.
3. Never declare an empty catch block.
4. Avoid nesting a try/catch within a catch block.
5. Always catch the most derived exception via exception filters.
6. Order exception filters from most to least derived exception type.
7. Avoid re-throwing an exception. Allow it to bubble-up instead.
8. If re-throwing an exception, preserve the original call stack by omitting the exception argument from the throw statement.
9. Only use the finally block to release resources from a try statement.
10. Always use validation to avoid exceptions.
11. Always set the innerException property on thrown exceptions so the exception chain & call stack are maintained.
12. Avoid defining custom exception classes. Use existing exception classes instead.
13. When a custom exception is required; Always derive from Exception not ApplicationException. Always suffix exception class names with the word “Exception”. Always add the SerializableAttribute to exception classes. Always implement the standard “Exception Constructor Pattern”. Always implement the deserialization constructor.
14. Always set the appropriate HResult value on custom exception classes. (Note: the ApplicationException HResult = -2146232832)
15. When defining custom exception classes that contain additional properties: Always override the Message property, ToString() method and the implicit operator string to include custom property values. Always modify the deserialization constructor to retrieve custom property values. Always override the GetObjectData(…) method to add custom properties to the serialization collection. 

### Events, Delegates & Threading

1. Always check Event & Delegate instances for null before invoking.
2. Use the default EventHandler and EventArgs for most simple events.
3. Always derive a custom EventArgs class to provide additional data.
4. Use the existing CancelEventArgs class to allow the event subscriber to control events.
5. Always use the “lock” keyword instead of the Monitor type.
6. Only lock on a private or private static object.
7. Avoid locking on a Type.
8. Avoid locking on the current object instance.

### Object Composition

1. Always declare types explicitly within a namespace. Do not use the default “{global}” namespace.
2. Avoid overuse of the public access modifier. Typically fewer than 10% of your types and members will be part of a public API, unless you are writing a class library.
3. Consider using internal or private access modifiers for types and members unless you intend to support them as part of a public API.
4. Never use the protected access modifier within sealed classes unless overriding a protected member of an inherited type.
5. Avoid declaring methods with more than 5 parameters. Consider refactoring this code.
6. Try to replace large parameter-sets (> than 5 parameters) with one or more class or struct parameters – especially when used in multiple method signatures.
7. Do not use the “new” keyword on method and property declarations to hide members of a derived type.
8. Only use the “base” keyword when invoking a base class constructor or base implementation within an override.
9. Consider using method overloading instead of the params attribute (but be careful not to break CLS Compliance of your API’s).
10. Always validate an enumeration variable or parameter value before consuming it. They may contain any value that the underlying Enum type (default int) supports.
11. Consider overriding Equals() on a struct.
12. Always override the Equality Operator (==) when overriding the Equals() method.
13. Always override the String Implicit Operator when overriding the ToString() method.
14. Always call Close() or Dispose() on classes that offer it.
15. Wrap instantiation of IDisposable objects with a “using” statement to ensure that Dispose() is automatically called.
16. Always implement the IDisposable interface & pattern on classes referencing external resources.
17. Avoid implementing a Finalizer. Never define a Finalize() method as a finalizer. Instead use the C# destructor syntax.

## Object Model & API Design

1. Always prefer aggregation over inheritance.
2. Avoid “Premature Generalization”. Create abstractions only when the intent is understood.
3. Do the simplest thing that works, then refactor when necessary.
4. Always make object-behavior transparent to API consumers.
5. Avoid unexpected side-affects when properties, methods, and constructors are invoked.
6. Always separate presentation layer from business logic.
7. Always prefer interfaces over abstract classes.
8. Try to include the design-pattern names such as “Bridge”, “Adapter”, or “Factory” as a suffix to class names where appropriate.
9. Only make members virtual if they are designed and tested for extensibility.
10. Refactor often!

## References

["MSDN: .NET Framework Developer’s Guide: Common Type System", Microsoft Corporation, 2004](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/cpguide/html/cpconthecommontypesystem.asp)

["MSDN: C# Language Specification v1.5", Scott Wiltamuth & Anders Hejlsberg, Microsoft Corporation, 2003](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/csspec/html/vclrfcsharpspec_15.asp)

["MSDN: Design Guidelines for Class Library Developers", Microsoft Corporation, 2004](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/cpgenref/html/cpconNETFrameworkDesignGuidelines.asp)

["MSDN: The Well Tempered Exception", Eric Gunnerson, Microsoft Corporation, 2001](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dncscol/html/csharp08162001.asp)

[Applied Microsoft .NET Framework Programming”, Jeffrey Richter, January 23, 2002, 1st ed., Microsoft Press, ISBN:
0735614229 “Which type should I use in C# to represent numbers?”, locabol, February 27, 2007, Luca Bolognese’s Weblog](http://blogs.msdn.com/lucabol/archive/2007/02/27/which-type-should-i-use-in-c-to-represent-numbers.aspx)