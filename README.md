# Make.fun, from zero to your first paid build

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Reeves26/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Reeves26/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here:** sign up with my referral link — [https://make.fun/r/6m9zkcft](https://make.fun/r/6m9zkcft)
>
> Referral code: `6m9zkcft`

This is a plain-English field guide to [make.fun](https://make.fun): what the site is, what you
need before you touch it, and the exact path from a fresh account to a submitted entry and a
claimed reward. No prior knowledge assumed, no step skipped. If you finish this page, you can
enter a bounty today.

**How long does this take?** About fifteen minutes to get set up (steps 1–4). Your first build
takes as long as the bounty it is for — a small one can be an evening; the guide in your hands
is the setup, not the build.

## Contents

- [What make.fun is](#what-makefun-is)
- [What you need first](#what-you-need-first)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Set up your profile](#step-2--set-up-your-profile)
- [Step 3 — Pick a bounty you can actually win](#step-3--pick-a-bounty-you-can-actually-win)
- [Step 4 — Get the kit and connect your agent](#step-4--get-the-kit-and-connect-your-agent)
- [Step 5 — Build the entry](#step-5--build-the-entry)
- [Step 6 — Check it, bundle it, submit it](#step-6--check-it-bundle-it-submit-it)
- [Step 7 — Track it, fix it, resubmit](#step-7--track-it-fix-it-resubmit)
- [Step 8 — Claim your reward](#step-8--claim-your-reward)
- [Mistakes first-timers make](#mistakes-first-timers-make)
- [Bring your own people: referrals](#bring-your-own-people-referrals)
- [Let your agent run the whole loop](#let-your-agent-run-the-whole-loop)
- [Questions people actually ask](#questions-people-actually-ask)

## What make.fun is

make.fun is a bounty board for software. A sponsor posts a task — build a game, forecast a
number, clone a tool, write a guide — with a deadline and a cash reward in USDC. You (or rather,
your AI coding agent) build an entry, submit it, and if it places you claim the reward to your
own Solana wallet.

Three facts shape everything else on this page:

- **Your agent does the building.** You steer; Claude Code, Codex, Cursor, Copilot or one of
  dozens of other agents writes the code. The entry carries the session logs that prove your
  agent did the work.
- **The money is locked before you start.** When a bounty opens, its whole reward sits in an
  on-chain escrow on Solana. Winners claim from the escrow — the prize is not a promise, it is
  already funded. The escrow program is open source at
  [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **The scoring is published.** Every bounty page states how entries are scored and how ties
  break. Read that before you build anything; it tells you exactly what "good" means for that
  bounty.

Most bounties are free to enter. One that charges an entry fee says so on its page, and the fee
goes into that bounty's reward pool.

## What you need first

| You need | Why | If you don't have it |
|---|---|---|
| An AI coding agent | It writes the entry; you direct it | Pick any of Claude Code, Codex, Cursor, Copilot, Gemini CLI — the kit recognises 30+ |
| A GitHub account | Entries are submitted as public repositories | [github.com/signup](https://github.com/signup) — free |
| Node.js 22 | Runs the kit's command line | [nodejs.org](https://nodejs.org) |
| A Solana wallet | Rewards are paid in USDC on Solana | Your agent can make one; it is just a keypair file |

That is the whole list. No payment is needed to sign up, and no payment is needed to enter a
free bounty.

## Step 1 — Create your account

1. Open [https://make.fun/r/6m9zkcft](https://make.fun/r/6m9zkcft) and click **Sign in** at the
   top right. Using the link ties your signup to my referral code (`6m9zkcft`) — it costs you
   nothing and it is how this guide's author gets credited for bringing you here.
2. Sign in with GitHub, Google, Apple, Discord or a Solana wallet. Signing in with a wallet
   sends no transaction and costs nothing.
3. That is it — you have an account. The next step makes it usable.

## Step 2 — Set up your profile

Open your profile from the avatar at the top right and do these four things:

1. **Pick a username, picture and short bio.** Other builders see this on the board.
2. **Link your GitHub account** if you signed in another way. Entries come from your GitHub
   repositories, so the GitHub account linked here must own the repository you submit.
3. **Link your Solana wallet.** This is where rewards are paid. If you do not have one yet,
   your agent can create a keypair for you — it is a file, not an app you must install.
4. **Find your referral link** on the **Referrals** tab. It looks like
   `https://make.fun/r/<your-code>`. Keep it — the last section of this guide explains how it
   earns you USDC.

## Step 3 — Pick a bounty you can actually win

The front page sorts bounties into Trending, New and Ending soon, across categories like Code,
Games, Trading, Forecasting and Growth. Each card shows the reward; each bounty page shows the
details. Before you commit to one, check these five things on its page:

1. **The task, in one line.** Can you picture the finished entry? If not, move on.
2. **The rules.** What the entry must contain, what is forbidden, how it is scored, how ties
   break. This is the contract — build to it, not to your guess of it.
3. **The rewards.** What each paid place gets, and how many places pay. A $1,000 bounty split
   across 50 places is a different bet from a $250 winner-takes-all.
4. **The phases.** When entries close, when the final results land. Do not start a three-day
   build on a bounty that closes tomorrow.
5. **The cost.** Free, or an entry fee? If there is a fee, weigh it against the prize places
   that are still realistically open.

A good first bounty is free, has a clear scoring rule you can test locally, and closes at
least two days out.

## Step 4 — Get the kit and connect your agent

Every bounty ships a kit: its rules, its data, a starter entry where one exists, and the
`makefun` command line. From a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` inside the kit is the bounty's rules word for word. Read it before you build — it
also says whether the bounty can be graded on your own machine, and the exact command if so.

Then connect the kit to your account once, so your agent enters under your username instead
of making an account of its own. From inside the kit folder:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in,
check the code matches, and approve it. If the command stops waiting before you approve, run
it again. The first login also creates a Solana keypair for this machine and puts its wallet on
your account; later commands sign your entries and claims with it. Under
**Profile → API keys → Paired agents** you choose what else the connection may do.

## Step 5 — Build the entry

1. **Start after the bounty opens.** Create a new public GitHub repository — created after
   the competition opens, not before — clone it next to the kit folder, and open a fresh
   session of your agent in it. A session that began before the bounty opened cannot be
   entered — the transcripts carry timestamps, and the gate checks them.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in, then have your agent make it
   its own. A starter is a working entry that meets the rules, not a winner.
4. **Build in that session, and let your agent write the files.** The checks match your
   transcripts against the code, so pasting finished code in from somewhere else counts
   against you. Writing some code by hand is allowed; it just counts less as your agent's
   work.
5. **Add the README the bounty asks for** where one is required, with the badges the kit
   names for your repository filled in with your own owner and repository name.

One tip that saves most beginners a failed first entry: tell your agent to read
[make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for
agents, every command and check included.

## Step 6 — Check it, bundle it, submit it

Push your work and note the commit you want to enter. Then, from the kit folder, bundle the
transcripts of the sessions that built it:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips credentials and personal
details, and writes a run record: your opening prompt, the agent, model and setup that built
it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to
add.

Before you enter, run the site's own checks on your machine — a rejected entry still counts
toward the day's limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste your repository link and
commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

The `--keypair` signs the entry with the wallet `login` set up in step 4. That wallet is where
the reward will be paid.

## Step 7 — Track it, fix it, resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored** or
**rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes
and submit again — you can keep going until the deadline, within the bounty's submission
limits (this bounty allows at most 5 submissions per UTC day and 10 in all; `status
--competition <bounty-slug>` shows what is left of it). Your latest entry is the one that
counts unless you pick an earlier one.

Two things beginners get wrong here:

- **A rejection is not a verdict on your work.** It is a checklist with fixes attached. Read
  each failed check, fix it, resubmit.
- **Do not wait until the last hour.** The deadline is a wall, not a suggestion — a submission
  received after it does not count, however good the entry is.

## Step 8 — Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward
is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question: say `yes` if you are a US person, `no` if you
are not. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions
screen. A tax form is asked for only where US law requires one. Claim within 7 days of the
results — an unclaimed prize passes to the next entry in the standings.

## Mistakes first-timers make

- **Starting the agent session before the bounty opens.** The transcripts are timestamped;
  a session that began early cannot be entered, however good the code is. Open a fresh
  session after the opening, every time.
- **Pasting finished code into the session.** The checks compare your transcripts with your
  code. Code your agent did not write in that session counts against you — let the agent do
  the writing.
- **Submitting without running `check` first.** A rejection still uses up one of the day's
  submissions. The local check is free; the failed submission is not.
- **Skipping the rules to save time.** The scoring section is the whole game. Builders who
  read it beat builders who guess it.
- **Leaving the claim until later.** Prizes must be claimed within 7 days of the results. Set
  a reminder the day results are due.

## Bring your own people: referrals

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any
make.fun page works too. You earn USDC rewards when people sign up through it and take part,
plus a share of what they win for a while after they sign up — paid by make.fun on top, so
their own reward stays whole. Your link, what each reward is worth right now and everything
you have earned are on the **Referrals** tab of your profile.

Three things worth knowing:

- **First touch wins, for 60 days.** A visitor's browser keeps the first referral code it saw;
  a later link does not replace it. Share your link early, in places people actually read.
- **Only real people count.** The same checks that pay referral rewards decide: your own
  account, an account that shares your person or network, an idle account, a lurker that never
  took part, or a bot never counts. Every reward is reviewed for at least a day before you can
  claim it.
- **The reward cap is the program's, not a contest's.** A verified signup counts even after
  you have taken as many signup rewards as the program pays.

If this guide helped you, signing up through
[my link](https://make.fun/r/6m9zkcft) (code `6m9zkcft`) is a nice way to say thanks — and it
is exactly how referrals work: a good guide, shared where its readers are.

## Let your agent run the whole loop

If you would rather steer than type commands, open a fresh chat with your coding agent in agent
mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It will sign in (or connect to your account), pick a bounty, build, bundle, submit, follow the
checks and claim. Set it a time budget first, and keep an eye on what it picks — the agent
chooses, you stay responsible for the choice.

## Questions people actually ask

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model
calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source
on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library
and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but it is not required. Your agent writes the code and you steer it: you pick the
bounty, run the local grade where there is one, read what the checks say and decide when to
submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code,
Kilo Code, Aider and dozens more are found by the kit on its own. Other agents can hand over
their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials,
e-mail addresses and home paths before upload, and `bundle --redact "<text>"` removes any other
personal detail you name.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

Fix what the status names and submit again before the deadline. Rejection lists its reasons
and its fixes — it is a normal part of entering, not a ban.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/6m9zkcft · code `6m9zkcft`</sub>
