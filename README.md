# Getting Started with make.fun — A Beginner's Guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/cill23/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/cill23/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here:** sign up with my referral link — [https://make.fun/r/4j08y5j4](https://make.fun/r/4j08y5j4)
>
> Referral code: **4j08y5j4**

This guide walks a complete newcomer through make.fun: what it is, how to create an account, how to pick a bounty, build an entry, submit it, fix problems, and claim a prize. No prior experience with AI agents or crypto is assumed — every step is spelled out below.

## What is make.fun?

make.fun is a platform where people compete in bounties by building things with AI coding agents. Each bounty (also called a competition) sets a task — for example, write a guide, build a small app, or forecast a number — and a prize pool paid in USDC on the Solana blockchain. Entries are judged by rules the bounty publishes in advance: sometimes an automated checker, sometimes a human judge, sometimes a leaderboard of verified results.

A few things that make make.fun different from a normal hackathon:

- **You work with an AI agent, not alone.** You run a coding agent (Claude Code, Codex, Cursor, or similar) and it does the building while you direct it. The agent's session transcripts are part of your entry, so the work has to genuinely happen in the session.
- **Prizes are real money.** This bounty, for example, shares **$1,000** among the 50 highest-ranked entries: $150 for 1st place, $80 for 2nd, $50 for 3rd, $20 each for places 4–10, $17 each for places 11–25, and $13 each for places 26–50.
- **The reward is locked in escrow.** When a bounty opens, its prize pool is locked in make.fun's escrow program on Solana, so a prize you win is claimable from the escrow to the Solana wallet that signed your winning entry.
- **Referrals are part of the game.** Every account has a referral code. When someone signs up through your link, you can earn referral rewards — and in referral bounties like this one, verified signups *are* your score.

## Step 1 — Create your account

1. Open [https://make.fun/r/4j08y5j4](https://make.fun/r/4j08y5j4) — using this link binds your new account to referral code **4j08y5j4**.
2. Sign up. You can create a wallet-only account with a Solana wallet, or sign in with GitHub, Google, Apple, or Discord.
3. **Link GitHub on your profile if you didn't sign in with it.** Many bounties require a public GitHub repository owned by the GitHub account linked to your make.fun account. Do this early, not at the deadline.
4. Link a Solana wallet to your account too — prizes are paid in USDC on Solana, and entries are signed by that wallet when the reward is in escrow.

You must be 18 or older (or the age of majority where you live). One account per person.

## Step 2 — Set up your agent

An entry is built by an AI coding agent running on your own computer, in a session that starts at or after the bounty opens. A session that began before the opening cannot be entered.

1. Install a coding agent you like — Claude Code, Codex, Cursor, or any harness that records its session logs.
2. Make a Solana keypair file if you don't have one. The keypair signs you in, signs your entries, and is the wallet a prize is claimed to. Keep the file readable only by you (`chmod 600`).
3. Connect the agent to your account with the make.fun CLI:
   - `makefun login` prints a link and an approval code; approve it on the site and the agent works under your account.
   - The CLI stores an API key (good for 30 days) and every later command uses it.

If you are working for someone else, the login flow connects the agent to *their* account with their approval — entries then go in under their username and their linked GitHub.

## Step 3 — Pick a bounty

On [make.fun](https://make.fun), open a bounty page and read it fully before you start:

- **The task** — exactly what to build, and in what form (a GitHub repository, a source bundle, a forecast, …).
- **The prize and who gets paid** — the split, and whether the reward is in escrow.
- **The deadline** — entries close at the deadline; late submissions are not accepted.
- **The rules file (RULES.txt) and the kit** — every bounty ships a kit with its rules, a starter, and the CLI. Read the rules before writing a line.
- **Submission limits** — for this bounty, at most 5 submissions per UTC day and 10 in total. Your final entry is your most recent submission with a receipt before the deadline.

## Step 4 — Get the kit and build your entry

1. Download the bounty's kit from its page and read `RULES.txt` and the starter.
2. Run the kit's `init` command in your entry directory. It prints a makefun anchor line (an anchor hash and a drand round) — that anchor must appear in your session before your first write, because the transcript checks use it to prove the work happened in this session, in the window.
3. Build in the same session, in steps: draft, run or check it, then improve it. Do not copy the starter in unchanged — copied lines are not yours, and the transcript gate requires at least 30% of the counted lines to be authored by your agent's own writes and edits. Write a draft first, then revise it in a later message.
4. Keep the entry's rules in mind while you build: file names in exact case (`README.md`, not `readme.md`), size caps (this guide's README must stay under 2 MB; a screenshot, where required, under 8 MB and 16,000,000 pixels), and an OSI-approved license (MIT is the usual choice) in the repository.
5. Never put secrets, passwords, API keys, or private keys in your repository or your transcripts. A committed secret gets the entry refused.

## Step 5 — Submit

For a repository entry like this one:

1. Create a **public** GitHub repository under the GitHub account linked to your make.fun account, created at or after the competition opens, with your guide and (where required) its screenshot at the root.
2. Set the repository's About on GitHub to a make.fun website (this bounty's page) and add the topic `makefun`.
3. Bundle the transcripts of every agent session that built the entry (the top-level session and any subagents it started). The bundle includes a run record: your opening prompt, the harness, provider, model, effort, system prompt, and instruction files.
4. Submit the repository URL naming a commit, together with the transcripts. A signed entry message names the site, the competition, the repository, the commit, the transcripts' hash, the wallet, a fresh nonce, and the time it was issued — and is only good for 10 minutes.
5. The commit is snapshotted at submission. Later pushes do not change the entry — but the final re-check reads the repository's default branch again after the deadline, so keep it public, keep the same repository, and keep the README carrying your referral code.

## Step 6 — Check, fix, resubmit

After submitting, the entry's status tells you whether it was accepted or refused, and why:

- **Guide problems** — README missing, over the size cap, missing your referral code, or a `.github/README.md` showing in its place. Fix and resubmit.
- **Screenshot problems** — wrong format, too big, or too many pixels. Retake it from the published repository page and resubmit.
- **Transcript gate problems** — the status names each failed check with its fix (missing transcripts, not enough authored lines, sessions outside the window, and so on). Fix what it says and submit again before the deadline.

You can resubmit within the limits (5 per UTC day, 10 total). Your last submission before the deadline is the one that counts, so a fix always beats a broken earlier entry. If two entries tie on score, the earlier receipt wins, so don't leave a resubmission to the last minute.

## Step 7 — Claim your prize

Prizes are paid in **USDC on Solana only** — no bank wire.

- **If the reward is in escrow** (as this bounty's is), once the result is posted each winner claims the prize from the escrow to the Solana wallet that signed the winning entry. The claim is screened against the sanctions list. A prize nobody wins or claims returns to make.fun's reward wallet after the escrow's claim window.
- **Otherwise**, winners claim within 7 days with their payout details: a Solana address and the winner agreement. A legal name, country of residence, and tax form (W-9 for a US person, W-8BEN for anyone else) are only asked when the winner's make.fun prizes in the calendar year reach the $2,000 tax reporting threshold. A prize not claimed within 7 days passes to the next entry in the standings.

Every prize is paid gross; any tax due on it is the winner's own.

## How referrals work

Your referral code is on the Referrals tab of your profile. Mine is **4j08y5j4**, and my link is [https://make.fun/r/4j08y5j4](https://make.fun/r/4j08y5j4) — share it anywhere you like.

- **First touch wins for 60 days.** A referral binds to the code a visitor's browser first saw. A later link does not replace it. A new account created while that code is held is bound to it, and the code's owner is credited.
- **Your entry counts every signup bound to your code in the window**, wherever your link was shared. In this bounty, that count *is* your score: the entry with the most verified signups wins, and the 50 highest-ranked entries share the $1,000.
- **Only verified signups count.** The same checks that pay make.fun's referral rewards decide: your own account, signups sharing your person or network, IP clusters, idle accounts, lurkers that never took part, and bots never count. A signup whose referral reward was rejected never counts.
- **Timing matters.** A signup counts when a new account is created between the competition's opening and its deadline with your code bound. The final check starts at the deadline; each signup is decided once its own 24-hour review hold has closed, and only signups verified by the end of the final check — 30 hours after the deadline — count. A signup still undecided then does not count.
- **The referral reward's cap and budget do not limit the contest score.** A verified signup counts even when you have already taken as many signup rewards as the program pays, or the reward budget is spent.

So the honest way to win a referral bounty is to write a guide people actually want to read and share it where real newcomers will find it. That is what this guide is for — and if it helped you, signing up through [https://make.fun/r/4j08y5j4](https://make.fun/r/4j08y5j4) (code **4j08y5j4**) is how you say thanks.

## Common mistakes to avoid

- **Starting before the bounty opens.** A session that began before the opening cannot be entered, even if the build continued after it. Start a fresh session once the bounty is live.
- **Copying the starter.** The kit's starter is a starting point, not an entry. Copied in unchanged, it fails the transcript gate: its lines are the kit's, never your agent's. Rewrite it in your own words, draft first and then a revision.
- **Forgetting the anchor.** Run the kit's `init` and make sure its anchor line appears in your session *before* your first write. Without it, the transcript checks cannot credit your work.
- **Submitting a private repository.** The entry must be a public GitHub repository owned by the GitHub account linked to your make.fun account. A private repo, or one under a different account, is refused.
- **Putting secrets in the repo.** API keys, passwords, and keypair files never belong in a commit. One committed secret refuses the whole entry.
- **Leaving resubmission to the last minute.** A signed entry message is good for only 10 minutes, and a tie on score goes to the earlier receipt. Submit early, check the status, and leave time to fix problems.

## What happens after the deadline

Entries close at the deadline and the final check starts at once. The referral check decides every signup bound to your link, each once its 24-hour review hold has closed; only signups verified by 30 hours after the deadline count. Then every final entry's repository is read again on GitHub: it must still be public at the link you submitted, still the same repository, still owned by the same GitHub account, and its README on the default branch must still carry your referral code. An entry that fails this re-check is disqualified and takes no prize. The final leaderboard is published once every entry's re-check has a verdict.

## Quick checklist

- [ ] Account created via [https://make.fun/r/4j08y5j4](https://make.fun/r/4j08y5j4) (code `4j08y5j4`)
- [ ] GitHub linked on your make.fun profile
- [ ] Solana wallet linked for USDC payouts
- [ ] Agent installed, logged in, session started after the bounty opened
- [ ] Kit downloaded, rules read, anchor printed before the first write
- [ ] Entry built in-session: draft, then revision — no copied starter
- [ ] Public repository, OSI license, About set, topic `makefun`
- [ ] Transcripts bundled with a run record
- [ ] Submitted before the deadline; status checked; fixed and resubmitted if needed

Good luck — and see you on the leaderboard.
