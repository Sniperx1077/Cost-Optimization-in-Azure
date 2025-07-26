We are working on a serverless architecture in Azure. One of our services stores billing records in Azure Cosmos DB (serverless mode).
The system is read-heavy, and we now have over 2 million records, with each record around 300 KB in size.
Records older than 3 months are rarely accessed, but when accessed, they must still respond within a few seconds.

Recently, our Cosmos DB costs have grown significantly, especially storage-related costs.
We need a cost-optimized solution that does the following:\n

Requirements:
No data loss

No downtime during transition

No changes to the existing read/write API contracts

Solution must be easy to implement and maintain (keep it simple)

Older records (> 3 months) can have slightly slower access, but must still be served when requested

Solution should ideally use serverless or pay-per-use components (e.g., Azure Functions, Blob Storage)

Can you propose a detailed, production-ready architecture that includes:

A tiered storage model (e.g., hot/cold tier)

A routing logic for reads that’s invisible to the client

A background archival job to move old records

Pseudocode or command examples

Optionally a simple architecture diagram and GitHub repo layout

This is part of a cost reduction initiative, and we need to demonstrate that the solution meets enterprise-grade reliability.
