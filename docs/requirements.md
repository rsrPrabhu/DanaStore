# Requirements

## User stories and acceptance criteria

### Order-status customer

**User story:** As a customer asking where my order is, I want an answer without waiting unnecessarily.

**Acceptance criteria:**

- The solution addresses “where is my order” chats.
- It uses order data from Ledgerline where order data is needed.
- It accounts for the fact that Ledgerline's carrier status is from the previous night's carrier file and may not be trusted in the morning.
- A customer who wants a real person can be served by a human agent.

### Support agent

**User story:** As a support agent, I want fewer repeated order-status chats and a consistent answer for the same case, so I do not answer these chats all day.

**Acceptance criteria:**

- The agent continues to work in ServiceNow; no new screen is introduced.
- The solution supports fewer customers asking the same thing twice as an experience measure.
- It supports the same answer for the same case.
- It does not leave agents to clean up after wrong answers.

### Customer asking about returns

**User story:** As a customer asking how to return an item, I want the applicable return answer for my market and delivery date.

**Acceptance criteria:**

- The answer considers market, delivery date, and policy.
- The applicable return rules are confirmed against the documented Confluence policy rather than assumed to match the agent's spreadsheet.

### Company customer

**User story:** As a company customer, I want contract-price questions handled quickly while keeping my company's terms private.

**Acceptance criteria:**

- A contract price is shown only to a customer entitled to see it.
- Buyer and manager roles are respected: a buyer places orders and a manager approves them.
- One company's private terms are never shown to another company.
- Price information comes from Atlas.

### E-commerce Engineering

**User story:** As the Engineering team responsible for the systems, we want a solution that is safe to operate and maintain.

**Acceptance criteria:**

- Ledgerline access starts read-only.
- The solution documents exactly what it reads and writes.
- Engineering reviews the code.
- The solution does not slow the ERP during a sale.
- It uses no account with more rights than needed.
- The code is understandable by Engineering.

## Non-functional requirements

- Keep using ServiceNow for the support team's workflow; do not add a new screen.
- Protect company contract terms from unauthorized disclosure.
- Apply least-privilege access and begin Ledgerline access requests promptly, recognizing they can take weeks.
- Prevent disruption to Ledgerline/ERP during sales periods.
- Provide the sponsor with short updates containing numbers and clear choices, without technical detail.
- Avoid public-facing incorrect policies or answers that worsen an already angry customer's experience.

## Open questions

- Is the estimate that four in ten chats are order-status questions supported by a ServiceNow sample?
- Do the personal return-window spreadsheet and the Confluence policy agree for every market?
- What refund amount requires human approval, and what rule does the Finance and Returns Controller set?
- What should happen for company customers with contract terms beyond the requirement to protect access?
- What data access can be approved by the Ledgerline owner/database administrator, and when?
- What requirements will the Finance and Returns Controller and Data Protection Officer add?
