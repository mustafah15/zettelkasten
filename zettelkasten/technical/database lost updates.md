---
tags:
  - database
type:
  - fleeting
related: "[[database read phenomenas]]"
---
lost update occurs when two different transactions are trying to update the same column on the same row within a database at the same time. Typically, one transaction updates a particular column in a particular row, while another that began very shortly afterward did not see this update before updating the same value itself. The result of the first transaction is then "lost," as it is simply overwritten by the second transaction.