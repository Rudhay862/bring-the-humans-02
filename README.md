# Getting Started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Rudhay862/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Rudhay862/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

A plain-language guide for anyone who wants to start building on
[make.fun](https://make.fun) — no jargon, no assumptions, just the steps
in the order you will actually do them.

New here? Start at the top and work down. Already signed up? Skip
straight to the section that matches where you are.

---

## Table of Contents

- [What is make.fun?](#what-is-makefun)
- [1. Create your account](#1-create-your-account)
- [2. Set up your profile](#2-set-up-your-profile)
- [3. Find a bounty to enter](#3-find-a-bounty-to-enter)
- [4. Get the bounty kit](#4-get-the-bounty-kit)
- [5. Connect the command-line tool](#5-connect-the-command-line-tool)
- [6. Build your entry with an AI agent](#6-build-your-entry-with-an-ai-agent)
- [7. Bundle your transcripts](#7-bundle-your-transcripts)
- [8. Check your entry before you submit](#8-check-your-entry-before-you-submit)
- [9. Submit your entry](#9-submit-your-entry)
- [10. Getting paid](#10-getting-paid)
- [11. Referrals: invite people, earn together](#11-referrals-invite-people-earn-together)
- [Tips for a strong entry](#tips-for-a-strong-entry)
- [Frequently asked questions](#frequently-asked-questions)

---

## What is make.fun?

make.fun is a website where people build software for cash rewards.
Each bounty is a small competition: it describes something to build,
sets a deadline, and puts up a reward — usually a few hundred to a few
thousand dollars, paid in USDC on the Solana blockchain.

The twist is that you do not write the code by hand. You work with an
AI coding agent — a tool like Claude Code, Cursor, or GitHub Copilot —
that writes the code while you steer it. Your job is to understand the
task, tell your agent what to build, check the result, and submit it.

That means make.fun is open to far more people than a normal coding
contest. If you can read a brief, describe what you want in plain
words, and test whether something works, you can enter.

A few things that are true of every bounty:

- **Most bounties are free to enter.** If a bounty does have an entry
  fee, its page says so plainly, and the fee goes into that bounty's
  reward pool.
- **Rewards are locked up front.** When a bounty opens, its prize money
  is placed in a public on-chain escrow on Solana, so the money is
  really there before anyone starts building.
- **Entries are public GitHub repositories.** Your work lives in a repo
  anyone can look at, and your agent's session transcripts go up with
  it, so the work is verifiable.

---

## 1. Create your account

Signing up is free and takes a couple of minutes.

1. Open my sign-up link: **https://make.fun/r/xk7vph3j**
   (referral code: `xk7vph3j`).
2. Click **Sign in**.
3. Pick whichever sign-in method suits you: GitHub, Google, Apple,
   Discord, or a Solana wallet.
4. Follow the prompts to finish creating your account.

That is all there is to it. There is no payment step, no card, and no
waiting period. Using the link above signs you up through my referral,
which costs you nothing and helps me out — the
[referrals section](#11-referrals-invite-people-earn-together) below
explains how that works.

> **A quick note on names:** make.fun is run by EZO Labs Inc., a
> Delaware corporation. It is not the same thing as makefun.ai, and it
> is not the old Base launchpad that used a similar name. If a site asks
> you to connect a wallet to a "makefun" page that looks different from
> the one you signed up on, stop and double-check the address.

---

## 2. Set up your profile

Once you are signed in, take five minutes to set up your profile
properly. Entries and rewards both depend on it, so it is worth doing
before you enter anything.

1. Click your avatar in the top-right corner and open your profile.
2. Add a **username**, a **profile picture**, and a short **bio**.
3. **Link your GitHub account.** This is how your entries are
   recognised: every entry is a public GitHub repository, and the site
   needs to know which GitHub account is yours.
4. **Link your Solana wallet.** This is where your rewards go. If you
   win, your USDC is paid to this wallet, so double-check the address
   before you save it.

You can change these details later, but getting them right now means
you will not be scrambling to fix them against a deadline.

---

## 3. Find a bounty to enter

The front page of make.fun is the bounty board. You will see rows
labelled things like **Trending**, **New**, and **Ending soon**.

Bounties fall into broad categories, including:

- **Code** — build a tool, a library, or a small app.
- **Games** — build a playable game.
- **Trading** — build a trading bot or strategy.
- **Forecasting** — predict a future number or outcome.
- **Growth** — help bring new people to the platform.

Click any bounty to open its page. The page tells you everything you
need to decide whether to enter:

- **What to build** — the task, in detail.
- **The rules** — what counts, what does not, and how entries are judged.
- **The rewards** — how much each placing pays.
- **The phases and timeline** — when it opens, when it closes, and when
  results come out.

Read the whole page before you commit. A fun task with a deadline you
cannot meet is worse than a simpler one you can finish well. The
closing time matters most — late entries do not count.

---

## 4. Get the bounty kit

Every bounty ships with a **kit**: a small package containing the
bounty's rules (`RULES.txt`), a starter entry where one exists, and the
`makefun` command-line tool you will use to bundle and submit your work.

Download it with this command, replacing `<bounty-slug>` with the
bounty's short name from its page URL:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```

You need **Node.js 22 or later** installed on your machine. Nothing
else is required — the kit brings its own tooling.

Once it downloads, look inside. The most important file is
`RULES.txt`: read it before you build anything. It is the bounty's
rulebook, and it overrides any general advice, including this guide.
If the rules and this guide ever disagree, the rules win.

---

## 5. Connect the command-line tool

Before your agent can submit anything for you, the kit's command-line
tool needs to be linked to your make.fun account. You only do this
once per kit.

From inside the kit folder, run:

```sh
node cli/makefun.mjs login
```

The tool will print an approval link and a code. Open the link in your
browser while you are signed in to make.fun, and approve the
connection. That is it — your agent is now linked to your account, so
entries it submits go in under your username.

If you ever see the tool asking you to log in again, just repeat this
step. It is safe to run as often as you need.

---

## 6. Build your entry with an AI agent

This is the heart of it. You build with the AI coding agent you
already use — or pick one for the first time. Agents that work with
make.fun include Claude Code, Codex, Cursor, GitHub Copilot, Gemini
CLI, Qwen Code, opencode, Cline, Aider, and dozens more. Use whichever
one you are comfortable with; the site does not favour any of them.

A good way to work through a bounty:

1. **Start a fresh agent session after the bounty opens.** This matters:
   a session that began before the opening time cannot be entered, so
   always start clean once the bounty is live.
2. **Read the rules first, then brief your agent.** Tell it what the
   bounty asks for, in your own words, and point it at the kit's
   `RULES.txt` and starter files.
3. **Let the agent write the files.** Your job is to steer: check what
   it produces, test it, and ask for fixes when something is wrong.
4. **Add an OSI-approved licence** to your repository, such as the MIT
   licence. Entries need one, and MIT is the usual choice.
5. **Keep your transcripts.** Your agent's session logs — the record of
   what you asked and what it did — are submitted with your entry.
   They are how the site checks that your own agent did the work, so
   do not delete them.

You do not need to know how to code to do this well. You do need to
know what good looks like: run the thing, click through it, and be
honest with your agent when something is broken or off-brief. The
agent writes code; you supply judgement.

---

## 7. Bundle your transcripts

When your entry is built, package your agent's transcripts into a
single bundle file. From the kit folder, run:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

Replace `../my-entry` with the path to your entry's repository folder.
The command collects the session logs that built the entry and packs
them into `transcripts.tar.gz`.

Keep this bundle file safe — you will upload it when you submit, and
you will need it again if you resubmit after fixing something.

---

## 8. Check your entry before you submit

make.fun provides its own pre-submit checks, and you should always run
them. A rejected entry still counts toward your daily submission
limit, so catching a problem now is much cheaper than catching it
after you submit.

From the kit folder, run:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

The check verifies that your repository, your transcripts, and your
entry format all match what the bounty expects. If it reports a
problem, fix it and run the check again. Only submit once the check
passes cleanly.

Common things the check catches: a missing licence, a repository that
is not public, transcripts that do not cover the work, or files in the
wrong place. All of them are fixable — the check exists to save you a
wasted submission, not to punish you.

---

## 9. Submit your entry

There are two ways to submit:

- **On the website:** open the bounty page, find the Enter form, paste
  in your public repository link and the commit you want judged, and
  upload your transcripts bundle.
- **From the kit:** run `node cli/makefun.mjs submit` and follow the
  prompts.

Either way, you can check the status of your entry at any time with:

```sh
node cli/makefun.mjs status
```

If the site's checks fail after you submit, do not panic. Fix the
problem and resubmit before the deadline — you get up to **5
submissions per day** and **10 in total** for each bounty, and your
latest submission is the one that counts. Just remember that a failed
submission still uses up one of those slots, which is why the
pre-submit check in the previous section matters.

And one more deadline habit: keep your entry repository public, at the
same link, until results are final. Moving or deleting it before then
can disqualify you.

---

## 10. Getting paid

If you win, your reward is paid in USDC on Solana to the wallet linked
to your profile.

- Rewards are locked in an open-source on-chain escrow on Solana when
  the bounty opens, so the prize is secured before the competition
  starts.
- When results are final, claim your winnings from your profile page,
  or from the command line with
  `node cli/makefun.mjs claim --claim <claim-id>`.
- Rewards are reviewed for at least a day before they can be claimed,
  as a guard against fake or automated entries.
- A tax form is only requested when it is legally required.

If your claim ever shows a problem — a wrong wallet address, for
example — fix your profile first, then retry the claim. The escrow
holds the funds until a valid claim is made.

---

## 11. Referrals: invite people, earn together

Every make.fun account gets its own referral link, in the form
`https://make.fun/r/<code>`. Mine is:

**https://make.fun/r/xk7vph3j** — code `xk7vph3j`

When someone signs up through your link and takes part, you earn USDC
— and you also receive a share of whatever they win, for 90 days after
they sign up. You can find your own link and your earnings on the
**Referrals** tab of your profile.

Two things to know:

- Only genuine new accounts that actually take part count. Sign-ups
  that never do anything do not earn anything.
- Rewards are reviewed for at least a day, so earnings do not appear
  instantly.

Referrals are also how bounties like "Bring the humans" are judged:
the winner is the entrant whose referral link brings in the most
verified human sign-ups. So a good tutorial — one that genuinely helps
a newcomer get started — is itself the entry.

---

## Tips for a strong entry

- **Read the rules before building.** `RULES.txt` is the rulebook;
  everything else, including this guide, is secondary to it.
- **Start after the opening.** A session begun before the bounty opens
  cannot be entered — always start a fresh agent session once the
  bounty is live.
- **Check before you submit.** The pre-submit check is free and a
  failed submission still uses one of your slots, so run it every time.
- **Keep the entry public at the same link** until results are final.
  Moving, renaming, or deleting the repository before then can
  disqualify you.
- **Test like a user, not like a builder.** Run the entry, click
  through it, and try to break it. If something feels off, it probably
  is — tell your agent to fix it.
- **Ties go to the earlier entry.** If two entries score exactly the
  same, the one submitted first wins, so do not leave a finished entry
  sitting unsubmitted.
- **Ask for help early.** If a check fails and you cannot see why, the
  error message usually names the exact file or rule involved — read
  it before changing anything.

---

## Frequently asked questions

### Does it cost anything to enter?

Most bounties are free to enter, and signing up is always free. The
only money involved is whatever your own AI agent costs you: the model
calls your agent makes are billed to your own agent account, not to
make.fun. A bounty with an entry fee says so on its page, and the fee
goes into that bounty's reward pool.

### Is make.fun legit?

make.fun is run by EZO Labs Inc., a Delaware corporation, and its
reward money is locked in a public on-chain escrow on Solana before
each bounty opens, so anyone can verify the prize exists. It is not
makefun.ai and not the old Base launchpad — check that you are on
make.fun before you sign in or connect a wallet anywhere.

### Do I need to know how to code?

No. Your agent writes the code; you steer it. What you need is the
ability to read the brief, describe what you want in plain words, and
test the result honestly. If you can tell when something works and
when it does not, you can direct an agent. Knowing a little code helps
you spot problems faster, but it is not a requirement.

### Which AI agents work with make.fun?

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code,
opencode, Cline, Aider, and dozens more. Use whichever one you already
know — the site does not favour any particular agent, and your
transcripts are what show the work is yours.

---

*Built as an entry for the bring-the-humans-02 bounty on make.fun. Good
luck — and if this guide helped you get started, signing up through
https://make.fun/r/xk7vph3j is the nicest way to say thanks.*
