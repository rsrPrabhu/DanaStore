# Problem statement

## Who has the problem

DemoStore customers need timely, reliable answers during sales, especially when asking where an order is or how to return it. Some customers are company customers with contract terms, and some explicitly want a human agent.

Customer Support agents carry much of the operational burden. They work in ServiceNow, but answering an order-status question can require copying an order number, checking Ledgerline, checking the carrier website, and manually changing a saved-reply date. For returns, at least one agent relies on a personal spreadsheet for market-specific return windows rather than the documented Confluence policy.

Customer Support leadership wants the team to spend less time on repeated order-status questions and to give the same answer for the same case. E-commerce Engineering owns the systems involved; Business Sales must protect company contract terms. The sponsor wants concise, numerical updates and clear choices.

## What it costs today

During sales, customers can wait up to 20 minutes. Marco estimates that about four in ten chats are “where is my order,” although this has not yet been validated against a ServiceNow sample. In 20 chats reviewed with agents, about half needed order data from Ledgerline.

The observed order-status chat took about four minutes, compared with the agent's initial estimate of two minutes. Ledgerline's status comes from the previous night's carrier file, which the agent does not trust in the morning, so the agent also checks the carrier's own website. A return chat for a German customer took about eight minutes while the agent checked market, delivery date, and policy.

The current experience can create repeat contact: the support measure of improvement is fewer customers who ask the same question twice. It also creates risk: inconsistent return rules may be used, a wrong answer can make an angry customer angrier, and company-specific contract prices must never be exposed to another company. The sponsor also risks spending on a tool that nobody uses, while Engineering risks affecting the ERP during a sale or leaving behind code its team cannot understand.
