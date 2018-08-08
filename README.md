# Coding Standards

## Table of content

 - Naming Conventions
 - Arrays
 - Classes & Constructors
 - Types
 - References
 - Objects
 - Destructuring
 - Strings
 - Functions
 - Variables

## Naming Conventions

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
