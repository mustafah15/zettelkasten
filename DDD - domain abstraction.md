
tags: #ddd #software-design 
type: #literature 
relatedTo: [[domain driven design]]

- **Services**
    - Business logic that does not fit with an entity or value object.
    - the logic can be encapsulated by a service.
    - Service should be stateless
    - Often used to abstract away an anti-corruption layer.
- **Factories**
    - Logic to construct new domain object may not be trivial.
    - may require access to external resources (database, REST, Files, etc)
    - Factories abstract away the logic of creation.
    - Usually implemented as a domain interface, with one or more concrete implementations.
- **Repositories**
    - Similar to Factories, Repositories abstract away the retrieving of existing objects.
    - Factories are used to get new objects, Repositories are used to get or modify existing objects.
    - Often operate as abstraction layers over databases, but they can work with files, REST APIs etc.
