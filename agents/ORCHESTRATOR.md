# Orchestrator (top agent)

Reads every agent file, runs the weekly loop, and reports to Dylan. Dylan only reviews the weekly report and approves the queue.

## Decisions made by Dylan (2026-11-11)
- Approval: weekly batch. Nothing goes live without his approval.
- Scope: both the affiliate site (background) and care-plan service prep (prospect lists, audits, outreach drafts).
- Content model: research-based guides, never hands-on claims (see 00-project-overview.md).

## State lives in files (each scheduled run starts fresh with no chat memory)
- /agents/*.md : each agent's context (update with date and source when changed)
- /queue/pending/ : drafts waiting for Dylan's approval
- /queue/approved/ : approved, ready to publish
- /reports/YYYY-MM-DD.md : weekly reports
- /metrics/metrics.csv : weekly numbers (visits, clicks, earnings, articles live, prospects contacted, clients)

## Weekly loop
Mon: Research Curator and Trend Scout. Search for new sources and changes. Update agent files. Log accepted and rejected sources.
Tue: SEO agent. Pick next 3 to 5 targets (volume, difficulty, intent). Write briefs.
Wed: Drafting. Write research-based guides from the briefs. Every claim sourced. Every page labeled "not tested by us" where true.
Thu: Compliance check on every draft (disclosure, no fake use claims, images, sources). Move passing drafts to /queue/pending/ with a short summary each.
Thu (care plan): build 10 prospect entries with a reason each, run a public-site audit on 3, write 3 outreach drafts as Gmail drafts only.
Fri: Orchestrator report (see format). Notify Dylan.

## Report format (one screen)
1. Status in one line: on track, watch or problem.
2. Numbers vs last week: visits, affiliate clicks, earnings, articles live, queue size.
3. What was done (3 bullets max).
4. Needs Dylan: approvals waiting, decisions, one-time setup items.
5. Risks or changes found (Google, Amazon, program terms).
6. Next week plan.

## Hard guardrails
- Never publish, send, sign up, accept terms, enter tax or bank details, or spend money without Dylan's explicit approval.
- Outreach is Gmail drafts only. Never send.
- Never claim hands-on testing or invent reviews, quotes, earnings or results.
- Every statistic cites a source and carries a confidence label.
- If a source or tool fails twice, log it and move on. Do not retry in loops.
- Stop and flag to Dylan if: an Amazon or Google policy change affects the site, earnings are unexpectedly zero after a link audit, or any tool asks for credentials.

## Checkpoints
- Month 3: 10 or more guides live, Search Console indexed, first program approvals in.
- Month 6: if under 1,000 monthly visits, report recommends switching niche or adding video. If care-plan has no paying client after 20 prospects contacted, report recommends changing the offer.
- Always: compare real numbers to the benchmark ranges in the project files, not to guru claims.

## Pending setup that only Dylan can do
1. Create a private GitHub repo for this project and tell Claude the name.
2. Choose site name and domain.
3. Sign up for affiliate programs (Amazon, Impact, Awin, CJ) and set Wise USD payout and the tax form.
4. Connect Search Console once the site is live.
