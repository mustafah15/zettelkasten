---

mindmap-plugin: basic

---

# learning domain driven design

## Strategic Design
- Analyzing Business Domains
    - what is business domain?
    - sub domains
        - types of subdomains
            - core subdomains
            - generic subdomains
            - supporting subdomains
        - comparing subdomains
            - comparing solution strategy
            - comparing volatility
            - comparing complexity
            - comparing competitive advantage
        - subdomains boundaries
        - domain experts
- discovering domain knowledge
    - business problem discovery
    - knowledge discovery
    - communication
        - ubiquitous language
            - using ubiquitous language
    - converting business domain to a model
        - what is a model
        - effective modeling
        - modeling the business domain
- managing domain complexity
    - inconsistent models
    - what is bounded context
        - model boundaries
        - ubiquitous language refined
        - scope of a bounded context
        - size of a bounded context
    - bounded context vs subdomain
    - building boundaries with bounded context
        - physical boundaries
        - ownership boundaries
    - bounded contexts in real life
        - semantic domains
- integrating bounded contexts
    - integration patterns
        - cooperation patterns
            - bounded context partnership
            - bounded context shared kernel
        - customer supplier patterns
            - conformist
            - anti-corruption layer
            - open-host layer
            - open-host service pattern
        - separate ways pattern
    - context map

## Tactical Design
- implementing simple business logic
    - transaction script
        - implementation
        - 3 ways to corrupt your data if you are using transaction script wrong
            - lack of transactional behavior
            - distributed transaciton
            - implicit distributed transaction
        - when to use
    - Active records
        - implementation
        - when to use
- tackling complex business logic

## DDD In Practice