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

## [[modules should be deep]]
- [[module abstraction]]
- [[modular design]]
    - [[module interface]]
    - [[module implementation]]
- [[deep modules]]
- [[shallow modules]]
- [[classitis]]

## [[information hiding and information leakage]]
- [[information hiding]]
- [[information leakage]]
    - [[how to prevent information leakage]]
    - [[information leakage types]]
- [[temporal decomposition]]

## [[general purpose modules vs special purpose modules]]
- [[general purpose module]]
    - benefits of general-purpose modules
- [[special purpose module]]

## [[different layer different abstraction]]
- [[pass-through methods]]
    - why pass-through methods are bad?
- [[pass-through variables]]
    - why do pass-through variables add complexity?
- [[when is interface duplication okay]]

## [[better together or better apart]]
- [[when to bring modules together]]
- [[general-purpose and special-purpose code separation]]
- [[module division and complexity]]
- [[splitting and joining methods]]
- [[code repetition]]

## [[better together or better apart]]
- [[module division and complexity]]
- [[general-purpose and special-purpose code separation]]
- [[when to bring modules together]]
- [[splitting and joining methods]]
- [[code repetition]]

## Code Comments
- [[why to write code comments]]
    - the four excuses not to write comments
        - [[the myth of good code is self-documented]]
        - [[i don't have time to write comments]]
        - [[comments get out of date]]
        - [[code comments might be worthless]]
- [[how to write better code comments]]
    - four comment types
        - [[low-level comments]]
        - [[higher-level comments]]
        - [[interface comments]]
        - [[implementation code comments]]
    - [[how to write better comments - pick conventions]]
    - [[how to write better comments - don't repeat the code]]
- [[write code comments first]]

## [[choosing names]]
- [[names should be precise]]
- [[names should be consistent]]

## [[modifying existing code]]

## [[benefits of code consistency]]
- ensuring consistency

## [[your code can be more obvious]]
- things that can make the code more obvious
    - consistency
    - comments
    - formatting
- things that can make the code less obvious
    - event driven programming
    - generic containers

## better design tips
- [[design it twice]]
- [[why exception adds complexity]]
- [[pull complexity downwards]]