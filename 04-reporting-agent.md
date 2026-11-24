# 04 · Read-only Claude reporting agent

A Claude agent that pulls Meta Ads data and writes the daily and weekly summary, so I spend time on decisions instead of spreadsheets.

## Guardrails

- **Read-only.** The agent can pull data. It cannot change budgets, pause ads or publish anything.
- **Humans decide.** Every recommendation is a suggestion; I make the change in Ads Manager.
- **No client data leaves the workspace.** Reports go to internal channels only.

## How it's set up

```
Meta Ads account
      │  (read-only connection via an MCP connector)
      ▼
Claude agent  ──►  Daily check  +  Weekly summary
```

1. Connect Claude to Meta Ads through a connector with **read-only** access.
2. Give the agent the account context: goals, target CPL, naming convention, budgets.
3. Run it on a schedule: a short daily check, and a full summary every Monday.

## Daily check prompt

```
Review yesterday's Meta Ads performance for [account].
Flag only what needs attention:
- Spend more than 20% above or below daily plan
- Any ad set with spend above [2x target CPL] and no leads
- Any ad with frequency rising and CTR falling vs its 7-day average
- Any tracking gaps (leads in Ads Manager but zero conversions recorded)
Keep it under 8 bullet points. If nothing needs attention, say so in one line.
Do not suggest changes to anything outside these checks.
```

## Weekly summary prompt

```
Write the weekly Meta Ads summary for [account], last 7 days vs the previous 7.
Structure:
1. Headline: spend, leads, CPL, cost per qualified lead (if available)
2. What changed and the most likely reason
3. Top 3 ads and bottom 3 ads, with one line on why
4. Creative fatigue watchlist
5. 3 recommended actions, ranked by expected impact
Use plain language. No jargon a founder wouldn't use.
```

## What it saves

- Daily monitoring: from a manual check to a short summary
- Weekly report: from building a spreadsheet to reviewing and editing a draft

## Next

- Add LinkedIn and Google to the same weekly summary
- Match leads to CRM outcomes for cost per qualified lead
