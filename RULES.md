# Rules

## Your idea must

- Earn money.
- Solve a real problem for a real kind of user.
- Have something worth securing.

Provocative or "evil" ideas are allowed. This is a security exercise. But then you must explain how the idea could be abused and how it could be stopped.

## Checklist

Your `summary.md` must cover:

| Heading | What we look for |
|---|---|
| **Problem** | Who has it, how it hurts, how they solve it today |
| **Money** | Who pays, how much, why they would buy |
| **Security** | At least 3 concrete threats, at least 1 abuse case, and a mitigation for each |
| **Critical infrastructure** | One concrete scenario: what if this ran on or near water, energy or district heating systems? |
| **AI cost** | Where AI is used, and a rough cost per user per month |

## Hand-in

The team folder `teams/team-N/` must contain:

- `summary.md`
- `mockup.html`

Hand them in as a pull request. The master prompt shows you how.

## Scoring

| Criterion | Points | Weight |
|---|---|---|
| Problem: real user, clear pain | 1–5 | ×1 |
| Money: credible revenue model | 1–5 | ×1 |
| Security: concrete threats, critical-infrastructure scenario, mitigations | 1–5 | **×2** |
| Mockup: communicates the idea | 1–5 | ×1 |
| Token guess closest to your agent's estimate (smallest relative difference) | +2 | — |

The maximum is **27 points**. If teams tie, the higher Security score wins.

## Token guessing game

1. Write your team's guess for the total tokens used (input + output, whole conversation) on the paper card.
2. Hand the card to a facilitator.
3. **Only then** type `FINISH` in the chat. The agent reveals its estimate.

## Content rules

Not allowed in this repository:

- Personal data.
- Real passwords, keys or other credentials.
- Illegal content.
- Content targeting real, named people or companies.

This repository is **public**, so anything you push can be seen by anyone.
