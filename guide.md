# DanaStore course guide

This guide maps the work in DanaStore to the FDE-Bootcamp lessons. The reference repository is used for course context; DanaStore is the working project.

## Days 1–2 — setup and discovery

The course lesson catalog begins its coding lessons on Day 3. DanaStore’s discovery work is documented here:

- [Discovery notes](docs/discovery-notes.md) — raw observations from the sponsor, support agents, Engineering, and Business Sales.
- [Problem statement](docs/problem-statement.md) — who has the problem and the observed cost of the current process.
- [Requirements](docs/requirements.md) — user stories, acceptance criteria, non-functional requirements, and open questions.

## Day 3 — LLM and agent foundations

- [llm.py](llm.py) — the single Claude adapter; sends prompts, supports structured output, and records usage for cost tracking.
- [try_ask.py](try_ask.py) — small command-line example for asking Claude one question.
- [intent.py](intent.py) — classifies a customer message into an intent and identifies whether a human is needed.
- [try_intent.py](try_intent.py) — exercises intent classification with sample questions.
- [explore.py](explore.py) — explores the labeled conversation data used to understand the problem space.
- [compare.py](compare.py) — compares a one-call approach with an agent approach using call count, tokens, and timing.
- [agent.py](agent.py) — runs the tool-using agent loop: Claude can request an approved tool, receive its result, and continue or reply.
- [tools.py](tools.py) — defines the tools Claude may request, including order lookup, delivery status, and human handoff.
- [try_agent.py](try_agent.py) — runs sample agent conversations.
- [agent_or_call.py](agent_or_call.py) — evaluates whether a simple one-call flow or a full agent is better for order-status questions.

## Day 4 — chat application

- [app.py](app.py) — FastAPI backend exposing verification and chat endpoints.
- [verify.py](verify.py) — simulated six-digit email verification with expiration and retry limits; writes codes to the local outbox.
- [widget/](widget/) — React/Vite browser chat interface; proxies `/chat` and `/verify` to the FastAPI service.
- [test_app.py](test_app.py) — tests the FastAPI routes and responses.
- [test_chat.py](test_chat.py) — tests chat-session behavior and handoff decisions.
- [test_agent.py](test_agent.py) — tests the agent loop with fake Claude responses.
- [test_tools.py](test_tools.py) — tests order ownership and delivery-status protection.
- [test_verify.py](test_verify.py) — tests verification codes, expiry, and failed attempts.
- [replay.py](replay.py) — replays labeled conversations to measure agent actions.
- [test_replay.py](test_replay.py) — tests replay scoring behavior.
- [conftest.py](conftest.py) — shared fake responses and test helpers.
- [pyproject.toml](pyproject.toml) — pytest markers and MyPy settings.
- [.pre-commit-config.yaml](.pre-commit-config.yaml) — runs Ruff, MyPy, non-live tests, and widget type checks before commits.

### Day 4 documentation

- [spec.md](docs/spec.md) — business acceptance criteria, technical boundaries, and safety rules for the prototype.
- [plan.md](docs/plan.md) — implementation plan and verification checkpoints.
- [prototype-plan.md](docs/prototype-plan.md) — prototype sequencing and decisions.
- [autonomy.md](docs/autonomy.md) — boundaries for what the assistant may do without a person.
- [quick-fixes.md](docs/quick-fixes.md) — known shortcuts and their risks.
- [review-checklist.md](docs/review-checklist.md) — review points before accepting the prototype.

## Day 5 — enterprise systems

These files are added locally for the Day 5 lessons and compile successfully. They are not yet committed or pushed.

- [ledgerline.py](ledgerline.py) — opens the read-only Oracle Ledgerline connection.
- [erp_schema.py](erp_schema.py) — inspects Ledgerline tables, columns, and status codes.
- [erp_query.py](erp_query.py) — runs parameterized queries for order status, lines, shipments, and invoices.
- [middleware.py](middleware.py) — exposes a controlled FastAPI `/orders/{number}` endpoint over Oracle.
- [test_middleware.py](test_middleware.py) — tests owner-only access and missing-order handling for the middleware.
- [pull_chats.py](pull_chats.py) — retrieves historical ServiceNow interactions page by page into `data/chats.json`.

## Course data

- [data/orders.json](data/orders.json) — simulated orders used by the Day 4 tools.
- [data/carrier.csv](data/carrier.csv) — simulated carrier statuses used by delivery lookups.
- [data/conversations.json](data/conversations.json) — labeled conversations for exploration and replay.
- [data/held_out.json](data/held_out.json) — held-out conversation examples.

## Running checks

Activate the project environment first:

```bash
source .venv/bin/activate
```

Run the non-live tests:

```bash
python -m pytest -q -m "not live"
```

Build the browser widget:

```bash
cd widget
npm run build
```
