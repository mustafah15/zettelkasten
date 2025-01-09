---
tags:
  - database
parent: "[[database transaction]]"
type: permanent
folgezettel: 3a2g3a
---

### why might need to do a read-only database transaction?
- **Consistency and data integrity**: By performing read-only transactions, you can ensure that the data you retrieve remains consistent throughout the transaction. It prevents any accidental modifications or updates to the data, maintaining the integrity of the database.

- **Security and audit purposes**: In certain scenarios, ensuring the data remains unchanged for security or auditing reasons is essential. For example, financial systems may require immutable records to maintain an accurate audit trail.