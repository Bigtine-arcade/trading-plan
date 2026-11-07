# Trading Plan — $26 → $5,000 Compounding Tool

A self-contained, mobile-first trading discipline tool that turns one aggressive
goal — growing **$26.00 into $5,000** — into a daily, trackable system. It combines
a compounding schedule, a position-size calculator, a hard-coded risk ladder, and
a printed daily checklist, so the plan is something you *follow*, not something
you *hope*.

**Live demo:** `https://<your-username>.github.io/<repo-name>/`

---

## The Goal

| | |
|---|---|
| Start equity | **$26.00** |
| Goal equity | **$5,000.00** (a 192× gain) |
| Goal date | **Friday, 29 January 2027** — last session before 1 Feb |
| Goal window | **56 trading sessions** (weekends + market holidays removed) |
| Required pace | **≈ +9.85% per session, compounded** |
| Bonus curve | The same rate continues to **Fri 19 Feb 2027** (session 70) — pure bonus once the goal is banked, risk capped at 2% |

The tool is honest about what this demands: the account must roughly **double
every 7.4 sessions**, and roughly **61% of all profit** comes in the final 10
goal sessions. Every screen reinforces one rule — *when you are behind, do not
chase with bigger size.*

## What's Included

### 1. `index.html` — the planner app

A single-file web app (no build step, no dependencies, works offline) with three tabs:

**Plan**
- Live equity, today's profit target ("Make today"), required pace %, and
  sessions remaining to goal.
- Position-size calculator for FX pairs, gold and BTC — enter the pair, stop in
  pips, and lot step; it returns risk %, risk in $, the exact **lot size**, and
  profit at target.
- A **risk ladder** that steps down as equity grows: 20% → 17% → 14% → 11% → 8% → 2%.
- Loss-streak protection: after one loss, next trade at 60% size; after two, 40%;
  after **three losses the sizer switches off** for the day.
- One-tap logging (Won / Lost / No setup today) with messages that tell you when
  to stop, when to shrink, and when the required pace has become unrealistic.

**Growth**
- Equity curve chart — your actual line vs the plan curve, on a log scale, with
  the 29 Jan goal marker.
- Standing vs plan, multiple of start, discipline stats (sessions used, flat-day
  streak, trades taken, win rate), and the next 5-session checkpoint.

**History**
- Full session log with per-day P&L and trade counts.
- Best/worst day and net summary.
- One-tap **JSON backup/restore** — the only record of your progress lives in
  your browser's localStorage, so export every Friday.

### 2. `schedule.html` — the printable "Make Today" sheet

A print-ready A4 sheet computing the exact profit required **per session** to stay
on the compounding curve:

- Full 70-session table: open, **Make today**, close, and gain — with the goal
  day highlighted and sessions 57–70 shown in blue as **bonus** targets.
- Weekly checkpoint table.
- The arithmetic box, milestone cards, and a "what this actually demands" section
  computed from the same math as the app — so the printed sheet and the app can
  never disagree.

Print it, pin it up, tick off each session.

---

## The Rules Baked Into the Tool

1. **The target is a stop, not a quota.** Hit today's line → done for the day.
2. **Never increase size to catch up.** Behind the line? Same size, extra days.
3. **Three losses = day over.** No "one more trade."
4. **After the goal, house money only.** Post-29-Jan trading is capped at 2% risk;
   losing there costs bonus, never the goal.
5. **Flat days cost $0.** No setup is a valid outcome — the tool recalculates
   pace and tells you honestly when the remaining curve is no longer realistic.

## Running It

No install, no build, no backend:

```bash
# any static server, or just open the file
open index.html          # macOS
# or double-click index.html
