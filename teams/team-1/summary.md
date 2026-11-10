# GOATS (Team 1)

One-liner: HeatSnitch — AI heat-theft detection for district heating utilities. An AI watchdog that watches every building's heat substation data and flags tenants who tamper with heat meters or bypass them — turning stolen heat into recovered revenue for the utility.

Tool used: OpenCode (GLM)

## Problem

- District heating utilities (huge in DK/SE — essentially every building in Copenhagen is on the grid).
- An estimated 3–7% of distributed heat is never billed: magnet-on-meter tricks, illegal bypasses, meter tampering, plus unreported distribution losses. Millions in lost revenue per city.
- The utility raises prices to cover the lost heat, so honest customers pay for it. When customers lose trust in the company they can't switch supplier — so some start cheating too. Theft breeds theft.
- A newspaper scandal about factories cheating their way out of paying for heat drives costs up for regular consumers, causes outrage and boycotts, and panics the board.
- Today: manual spot checks, tips from meter readers, and crossed fingers. Nobody can audit 100,000+ substations by hand.

## Money

- The utility pays, not the tenant.
- Flat fee of €5 per substation per month (we dropped the success fee because getting paid per accusation gives the wrong incentive). Optional alternative: success fee ~20% of recovered revenue.
- Our maths: 100,000 substations × €5 × 12 months = €6M per year.
- One caught heat thief pays for the service for years. Pure ROI story.

## Security

- Consumption data reveals when a flat is empty. Burglars could buy/leak the data → burglary reconnaissance ("HeatSnitch as a burglar's oracle"). Mitigation: data stays on-prem at the utility, per-unit data never exported, strict access logging.
- A landlord weaponizes a "theft flag" to evict or harass a tenant, or an adversary spoofs telemetry to frame a neighbour. Mitigation: alerts are indicators only — signed meter data + mandatory human audit with explainable evidence before anything happens.
- MITM/replay attack on the substation telemetry (old Modbus/serial links): attacker replays "normal" data to hide their own theft or smear someone else. Mitigation: signed telemetry + device attestation; alarm when data looks too clean.
- Evil twist: the same anomaly model run in reverse — a leaked dashboard shows attackers which buildings are easy to steal heat from, or when offices sit empty. Mitigation: no raw model scores exposed to end users, rate-limited queries, query auditing.
- The system flags a suspect meter, never a person — the utility's control team decides, including on-site checks.

## Critical infrastructure

- District heating is critical infrastructure (KRITIS-listed in the EU).
- Scenario: a state actor uses the platform's remote read-access to substations as a pivot into grid OT — or floods operators with mass-spoofed tamper alerts during a January cold snap, forcing crews to disconnect buildings and leaving elderly residents without heat.
- What we would do differently: read-only integration, zero remote-control capability, network-segmented deployment.

## AI cost

- Anomaly detection on flow/return temps + consumption curves: a small time-series model, ~24 values/day per substation. The LLM is only used to draft the human-audit report.
- ≈ €0.05–0.20 per user per month — trivially covered by the subscription.

## What we changed after being challenged

- We switched the 20% success fee to a flat fee after being challenged on the incentive to accuse — the reward for false accusations is now designed out of the pricing.
- We stopped "flagging tenants/suspects" and now flag a suspect meter — the utility's control team decides, not the AI.
- We replaced the vague "customer trust" consequence with a concrete spiral: customers can't switch supplier, so honest ones start cheating too and the theft grows every year.
- We made "a scandal" concrete: a newspaper story about factories cheating → public outrage and boycotts → the CEO/CFO signs to make the story go away.
- We did the maths ourselves: 100,000 × €5 × 12 = €6M/year, and checked it against the 3–7% of heat that is unbilled.

## Security game

Not played

## Token estimate

Input: ~8,000 tokens · Output: ~6,000 tokens · Total: ~14,000 tokens · Estimated cost: 0.11 USD

(Estimate only - hidden system prompts and re-sending the conversation every turn make the real cost higher.)
