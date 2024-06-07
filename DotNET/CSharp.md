# DotNET C\#

## Styling

### Naming

- Avoid acronyms and abbreviations unless the abbreviation is much more widely used than the long form.
- When converting nouns to identifiers (mixed casing): avoid all caps words longer than 3 characters, unless it is a single word -
    ("Namespace.ACRONYM.ClassName" OK, "Namespace.ACRONYMBase.ClassName" NO => "Namespace.AcronymBase.ClassName")

#### Types

- PascalCase (mixed case with the first letter of each internal word capitalized).
- Use nouns.
- Prefer singular nuons, including those used for collections.

##### Suffixes

- "Base" suffix for abstract classes (optional but recommended).
- "Helper" suffix for static classes that contains utility methods used only in a particular context (visibility limited to usually assembly level at most).
- "Utility" suffix for static classes that contains utility methods used in multiple contexts (usually exported from a library).

#### Type Members

- Contants: Nouns, PascalCase.
- Fields (readonly): Nouns, PascalCase.
- Fields: Nouns, camelCase.
- Indexers: Nouns, PascalCase.
- Properties: Nouns, PascalCase.
- Events: Nouns, PascalCase.
- Methods: Verbs, PascalCase.

##### Prefixes

- Prefix field names with "_" only if not public and only to avoid name clashes.
- Prefix method names with "Handle" for event handlers.
- Prefix method names with "On" for hooks.

##### Suffixes

- Suffix method names with "Internal" only if not public and only to avoid name clashes.

#### Local Variables

- camelCase (mixed case with the first letter lowercase, with the first letter of each internal word capitalized).

### Order of Members

#### Within a class, struct or interface

- Enums (Nested)
- Interfaces (Nested)
- Structs (Nested)
- Delegates (Nested)
- Records (Nested)
- Classes (Nested)
- Constants
- Fields
- Indexers
- Properties
- Events
- Constructors
- Destructors (Finalizers)
- Methods

##### Within each of these groups, order by static, then non static, where applicable (fields, properties, events and methods)

- Static
- Non Static

##### Within each of these groups, order by access

- Private
- Private Protected
- Protected
- Protected Internal
- Internal
- *Explicit Implementation*
- Public

##### Within each of these groups, order by readonly, then non readonly, where applicable (fields)

- Readonly
- Non Readonly

### Method Bodies

- Prefer static local methods.
- Place local methods at the top of the body if possible.
- Omit braces in control flow only if using one line only and terminal only statements (return, break, continue).


### Method Invokation

#### Keyword Arguments

Introduce parameter names for argument represented by keywords.
Eg. GC.SuppressFinalize(this) NO => GC.SuppressFinalize(obj: this) OK;
