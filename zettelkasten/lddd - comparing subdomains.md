---
tags:
  - book-notes
  - ddd
related: "[[lddd -  analyzing business domains]]"
aliases:
  - comparing subdomains
type:
  - literature
---
## comparing subdomains 
let's explore the difference between the three subdomain types from different angels 

### competitive advantage 
- Only core subdomains provide a competitive advantage to a company, 
- Generic subdomains by definition cannot be a source for any competitive advantage as these are generic solutions the same solution used by the company and its competitors 
- supporting subdomains have low entry barriers and cannot provide a competitive advantage either, usually a company wouldn't mind if its competitors copied its supporting subdomains 
### complexity 

Different types of subdomains have different levels of complexity when designing software we have to choose tools and techniques that accommodate the complexity of the business requirement therefore identifying subdomain complexity is essential for designing a sound software solution
- Core subdomains are complex they should be as hard for competitors to copy as possible the company's profitability depends on it. that is why strategic companies are looking to solve complex problems as their core subdomains. 
- Generic subdomains are much more complicated compared to the supporting domains there should be a good reason why the company already invested time and effort in solving these problems. these solutions are neither simple nor trivial, consider for example encryption algorithms or authentication mechanisms.
- Supporting subdomain business logic is simple often it does not go beyond validating inputs or converting data from one structure to another.
![[Screenshot 2024-01-25 at 08.17.26.png]]
### volatility 
- core subdomains can change often if a problem can be solved on the first attempt, it's probably not a good competitive advantage competitors will catch up fast. consequently, solutions for core subdomains are emergent. Different implementations have to be tried out, refined, and optimized moreover the work on. core subdomains are never done, companies continuously innovate and evolve core subdomains
- contrary to the core subdomains supporting subdomains do not change often they do not provide any competitive advantage for the company
- despite having existing solutions generic subdomains can change over time the changes can come in the form of security patches bug fixes or entirely new solutions to generic problems.
### solution strategy 
- core subdomains have to be implemented in-house they cannot be bought or adopted which would undermine the notion of competitive advantage, as the company's competitors would be able to do the same. it would be unwise to outsource the implementation of a core subdomain as it is a strategic investment and since core subdoamins are expected to change often and continuously, the solution must be maintainable and easy to evolve, thus core subdomains require implementation of the most advanced engineering techniques. 
- Since generic subdomains are hard but already solved problems it's more cost-effective to buy an off-the-shelf product or adopt an open-source solution than invest time and effort into implementing a generic subdomain in-house. 
- supporting subdomains do not require elaborate design patterns or other advanced engineering techniques a rapid application development framework will suffice to implement the business logic without introducing accidental complexities. ![[Screenshot 2024-01-25 at 08.41.01.png]]