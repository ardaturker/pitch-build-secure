# Facilitator runbook

This is for the two facilitators. Students are welcome to read it too: the scoring is no secret.

## Prep (before the day)

- [ ] Ask the students to create a GitHub account beforehand: <https://github.com/signup>.
- [ ] Set up 2–3 spare lab laptops with a browser and a logged-in chat agent.
- [ ] Prepare 5 paper guess cards, **pre-numbered Team 1–5**, with fields: team name and token guess. The card number is the team's number and folder. The agent's estimate ends up in the team's `summary.md`.
- [ ] Print 2 copies of the scorecard below.
- [ ] Dry-run [MASTER-PROMPT.md](MASTER-PROMPT.md) in at least 2 different chat tools, and open a test PR from a non-owner account.
- [ ] Check that GitHub Pages is **off**.

## Day-of script

| Min | Facilitators do / say |
|---|---|
| 0–5 | Show this repo on the big screen. Explain the goal (money + user problem + security + critical infrastructure). Say: "Pick a driver, open MASTER-PROMPT.md, paste it, follow the agent." Hand out one numbered guess card per team: "Your card number is your team number." |
| 5–15 | Walk around. Help teams that are stuck on an idea. Check that every team has given the agent its team number. |
| 15–30 | Listen in on the security answers. Challenge vague ones: "Which attacker? Protecting what?" At 25 min, call "5 minutes left for the checklist". |
| 30–35 | Teams design their main screen and the agent builds `mockup.html`. Nudge teams that are still in the checklist. |
| 35–40 | Collect the guess cards **before** teams type `FINISH`. Teams that have time play the optional Security Game first. Merge PRs as they arrive, after a quick glance (see the merge routine). Help with GitHub, and use the fallback if a team is stuck. |
| 40–50 | Run the 1-minute pitches from each team's mockup on screen. |
| Buffer | Remind everyone to fork the repo now if they want to keep their work. Send them to lunch. |

## Merge routine (from minute 30)

- Open **Pull requests** and glance at the files: right folder, no personal data, no credentials, nothing obviously offensive.
- Check that the team name in the `summary.md` heading matches the card for that folder. If two PRs target the same folder, ask the teams before merging either one.
- Merge. The real review happens over lunch.

**Fallback:** if a team can't open a PR, the driver shows you both files (e.g. via a shared chat or USB stick). You add them under `teams/team-N/` with **Add file → Create new file** and commit them directly.

## Lunch routine (~30 min)

1. Review every `teams/team-N/` folder properly. Remove or fix anything that breaks the content rules in [RULES.md](RULES.md).
2. Open each `mockup.html`. Use **Raw → save**, or turn on Pages (step 3) and use the URL.
3. Enable GitHub Pages, so the mockups have URLs for the announcement:

   ```bash
   gh api -X POST repos/moller90/pitch-build-secure/pages -f "source[branch]=main" -f "source[path]=/"
   ```

   Mockup URL: `https://moller90.github.io/pitch-build-secure/teams/team-N/mockup.html`

4. Fill in the scorecard. Give +2 to the team whose paper guess is closest to the total in the **Token estimate** section of its own `summary.md`, measured as relative difference. Use **What we changed after being challenged** and **Security game** to judge how much the team thought for itself.
5. Pick: the winner, the best security insight, and the closest guess.

## Announcement (5 min)

- Show the winning mockup via its Pages URL.
- Mention the best security insight.
- Mention the closest guess. Point out that agents estimate differently, and that hidden system prompts and resent context make the real cost higher.

## After the event

Forks stay public after the repository is deleted. In the buffer before lunch, ask every driver to delete their fork (**Settings → Delete this repository**) unless they want to keep it. Make sure no fork holds content you removed over lunch.

Delete the repository:

```bash
gh auth refresh -h github.com -s delete_repo
gh repo delete moller90/pitch-build-secure --yes
```

## Scorecard

| Criterion | Weight | Team 1 | Team 2 | Team 3 | Team 4 | Team 5 |
|---|---|---|---|---|---|---|
| Problem (1–5) | ×1 | | | | | |
| Money (1–5) | ×1 | | | | | |
| Security (1–5) | ×2 | | | | | |
| Mockup (1–5) | ×1 | | | | | |
| Closest guess | +2 | | | | | |
| **Total (max 27)** | | | | | | |

If teams tie, the higher Security score wins.

Best security insight: ______________________________________________

## Fallback plan

If GitHub or the network fails on the day, use Plan B (1 laptop per team, no GitHub). It is kept outside this repository.
