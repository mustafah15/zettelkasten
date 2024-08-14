---

mindmap-plugin: basic

---

# A Philosophy Of Software Design

## complexity in software design
- Fighting Against Complexity
    - by eliminating complexity
    - by encapsulating complexity
- The Incremental Nature of Complexity
- Causes Of Complexity
    - dependencies
    - obscurity
- Symptoms of Complexity
    - change amplification
    - cognitive load
    - unknown unknowns

## working code is not enough
- Tactical Programming
    - tactical tornado
- Strategic Programming
    - strategic programming investment
        - Investment types
            - reactive
            - proactive
        - How Much to Invest

## [[POSD - modules should be deep]]
- [[module abstraction]]
- [[modular design]]
    - [[module interface]]
    - [[module implementation]]
- [[deep modules]]
- [[shallow modules]]
- [[classitis]]

## [[POSD - information hiding and information leakage]]
- [[POSD - information hiding]]
- [[POSD - information leakage]]
    - [[how to prevent information leakage]]
    - [[POSD - information leakage types]]
- [[POSD - temporal decomposition]]

## [[POSD - general purpose modules vs special purpose modules]]
- [[general purpose module]]
    - benefits of general-purpose modules
- [[special purpose module]]

## [[POSD - different layer different abstraction]]
- [[pass-through methods]]
    - why pass-through methods are bad?
- [[pass-through variables]]
    - why do pass-through variables add complexity?
- [[POSD - When is interface duplication okay?]]

## [[POSD - better together or better apart]]
- [[POSD - Bring Modules Together If]]
- [[POSD - separate general-purpose and special-purpose code]]
- [[POSD - Module Division and Complexity]]
- [[POSD - Splitting and Joining Methods]]
- [[POSD - Code Repetition]]

## [[POSD - better together or better apart]]
- [[POSD - Module Division and Complexity]]
- [[POSD - separate general-purpose and special-purpose code]]
- [[POSD - Bring Modules Together If]]
- [[POSD - Splitting and Joining Methods]]
- [[POSD - Code Repetition]]

## Code Comments
- [[POSD - why write comments]]
    - the four excuses not to write comments
        - [[POSD - the myth of good code is self-documented]]
        - [[POSD - i don't have time to write comments]]
        - [[POSD - comments get out of date]]
        - [[POSD - comments might be worthless]]
- [[POSD - how to write better comments]]
    - four comment types
        - [[POSD - low-level comments]]
        - [[POSD - higher-level comments]]
        - [[POSD - interface comments]]
        - [[POSD - implementation comments]]
    - [[POSD - how to write better comments - pick conventions]]
    - [[POSD - how to write better comments - don't repeat the code]]
- [[POSD - write comments first]]

## [[POSD - choosing names]]
- [[POSD - names should be precise]]
- [[POSD - names should be consistent]]

## [[POSD - modifying existing code]]

## [[POSD - consistency]]
- ensuring consistency

## [[POSD - could be more obvious]]
- things that can make the code more obvious
    - consistency
    - comments
    - formatting
- things that can make the code less obvious
    - event driven programming
    - generic containers

## better design tips
- [[POSD - design it twice]]
- [[POSD - define errors out of existence]]
- [[POSD - pull complexity downwards]]