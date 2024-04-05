# DotNET C\#

## Styling

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

- *Explicit Implementation*
- Private
- Private Protected
- Protected
- Protected Internal
- Internal
- Public

##### Within each of these groups, order by readonly, then non readonly, where applicable (fields)

- Readonly
- Non Readonly
