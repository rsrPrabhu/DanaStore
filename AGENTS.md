# DanaStore working instructions

## Planning before changes

Before changing application code, configuration, dependencies, Docker files, or project documentation:

1. Inspect the relevant files.
2. Present a concise plan describing the files to change, the intended change, and verification.
3. Wait for the user's explicit approval before making the change.

## Project boundary

- Make all DanaStore changes only in this repository.
- Use `/Users/prabhakaranrajan/Development/FDE/FDE-Bootcamp/` as reference material only.

## Secrets and safety

- Never print, commit, or send values from `.env` files or API keys.
- Keep `.env` and `.venv` excluded from Git.

## Application guardrails

- Route every Anthropic/Claude model call through `llm.py`; keep the selected model in that module.
- Run tests that make live Claude API calls only when the user explicitly approves the cost and data sharing involved.
- Start, stop, or change Docker services only when the user explicitly requests it.
- Ledgerline access is read-only. The only permitted write is an approved return draft to `LL_RTN_REQ_STG` through the writer account.
- A refund is always a draft requiring human approval; never promise a completed payment, credit, or compensation.
