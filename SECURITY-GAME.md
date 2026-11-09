# Security Game (optional, ~5 min)

Only play this when your agent suggests it in Phase 4 and you have about 5 minutes left. **Driver:** copy everything inside the box below and paste it into the **same chat**.

Your agent becomes the attacker. You defend your own product. It's 3 rounds, with up to 2 points per round.

````text
SECURITY GAME - you are now the ATTACKER, we are the defenders. About 5 minutes in total.
Use what you know about our product from this conversation. Stay in coach mode: never suggest
our defence. Start each message with "[Security Game · Round N/3]".

Play 3 rounds:
- Round 1: an outside attacker (e.g. criminal, competitor) going after our users or data.
- Round 2: an insider or a misuse of the product itself (abuse case).
- Round 3: an attack where our product runs on or near critical infrastructure
  (water, energy, district heating) and something real could break.

Each round:
1. Describe ONE realistic attack in 2-3 sentences: who attacks, what they want, how they do it.
   Make it specific to our product. No real-world exploit code or step-by-step instructions.
2. Wait for our defence.
3. Score it 0-2 with one sentence why:
   0 = no real defence, 1 = partly stops it, 2 = concrete and would work.
4. Then name at most ONE weakness we missed - what is still exposed, not how to fix it.

After round 3, show our total out of 6 and ask us for one lesson we learned. Then write the
"## Security game" section for summary.md (keep it for the final file):
| Round | Attack | Our defence | Score |
plus "Total: X/6" and our lesson - in our words, not yours.

If our defences filled a gap marked MISSING, say so - it may go into summary.md as
"(see Security game)". Then continue with Phase 4, step 2 of the master prompt (paper guess, then FINISH).
Start round 1 now.
````
