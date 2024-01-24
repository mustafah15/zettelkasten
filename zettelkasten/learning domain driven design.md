---
tags:
  - book
  - book-notes
  - ddd
  - software-design
related: "[[domain driven design]]"
type:
  - literature
---
## what is a business domain?
A business domain defines a company's main area of activity, generally speaking, it's the service the company provides to its clients. it's important to note that companies may change their business domain often. 
## what is a subdomain?
To achieve its business domain's goals a company has to operate in multiple subdomains, and a subdomain is a fine-grained area of business activity, it's just one building block in the overarching system. The subdomains have to interact with each other to achieve the company's goals in its business domain. 

## types of subdomains
subdomains bear different business values, domain driven design distinguishes between three types of subdomains: core, generic and supporting. 

### core subdomain 
A core subdomain is what a company does differently from its competitors (the interesting problems)

#### complexity 
A core subdomain that is simple to implement can provide a short-lived competitive advantage. therefore core subdomains are naturally complex.

#### source of competitive advantage
It's important to note that core subdomains are not necessarily technical. not all business problems are solved through algorithms or other technical solutions a company's competitive advantage can come from various sources. 
Imagine a company that specializes in manual fraud detection the company trains its analysts to go over documents and flag potential fraud cases, if you are building the software system that analysts are working with, is that a core subdomain? No. the core subdomain is the work the analysts are doing. the system you are building has nothing to do with the fraud analysis.


> [!NOTE] core subdomain VS core domain
> Core subdomains are also called core domains to avoid confusion we will call it core subdomain 


### generic subdomains 

### supporting subdomains 
