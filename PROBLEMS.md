# Problems this solves

## The short version

**The hard part of opening a pharmacy isn't the pharmacy. It's holding the whole process
in your head at once.**

Standing up a community pharmacy in the Philippines means interleaving FDA licensing, DTI/SEC
registration, Barangay and Mayor's permits, BIR registration, zoning checks, lease terms,
capital planning, supplier accreditation, FDA-compliant layout, a launch inventory, and the
records you're legally required to keep. There is **no published order** to any of it, and
the authorities don't hand you a critical path — they hand you forms.

Three specific failures follow from that:

| Failure | What it looks like in practice |
|---|---|
| **You can't tell which phase you're in.** | You spend a week on layout drawings while a permit you needed first is still unstarted. Nothing is *wrong*; the sequence is. |
| **You don't know what "done" means.** | Every step is "some paperwork". There's no checkbox, so there's no moment where you can stop thinking about it. |
| **Progress is invisible for months.** | A goal measured in months with no visible progress loop dies quietly. This is the failure that actually ends most setups. |

The last one is the real one. Opening a pharmacy is a long-horizon project whose effort is
front-loaded and whose reward is far away — exactly the profile where motivation fails
before the project does.

## What this replaced

| Before | After |
|---|---|
| Requirements spread across FDA circulars, LGU counters, supplier emails and advice from whoever you last talked to | Seven phases in order, with 24 entries covering what each one actually requires |
| No sense of sequence — the order was whatever you encountered first | `00 Before You Have a License` → `06 Physical Setup` → `Ongoing` check-ins, worked in order |
| "Some paperwork" with no completion state | Each entry ticks off, and the tick is remembered |
| You don't know what's left until you try to remember it all | Progress is on screen, so the remaining work is a list rather than a feeling |
| Numbers scraped from forums (fees, capital ranges, salaries) with no source | Floor-area minimums, document lists and fee/capital ranges collected into the entry they belong to |
| Already-registered pharmacists still reading the pre-license phase | An **"I'm a licensed RPh"** toggle that hides that phase entirely — the guide adapts to where you actually are |
| Long-horizon goals with no progress loop | A **quest board**. Deliberately gamified, because a months-long goal needs a visible loop or it loses momentum |

## The design decisions worth pointing at

**Phases, not a checklist.** A flat checklist of 24 items tells you *what* to do and nothing
about *when*. Seven ordered phases make the current step obvious and make out-of-order work
visible as a mistake rather than a preference.

**Progress is local.** Ticked entries, expanded panels and theme live in `localStorage` on
your device. No account, no server, no analytics. A business plan is not something you sign
up to track.

**One file, no build.** Plain HTML/CSS/JS — open `index.html` and it runs. There is nothing
to install, nothing to keep updated, and nothing that breaks when a dependency moves. This
needs to still open in five years.

**It prints as an actual document.** `Ctrl/Cmd-P` produces the whole guide in strict reading
order with every entry expanded. A plan you can hand to a partner, a landlord, or your own
bank is a different artefact from a web page.

**Tags do real work.** *Daily*, *one-time*, *weekly* and *high-priority* aren't decoration —
they're what makes the weekly check-ins meaningful, and they let you reset the daily set
without touching one-time completions.

**The caveats are in the README, not buried.** Fees, salaries and requirements reflect
2025–2026, and the README says to confirm against the live FDA (CDRR) checklist and your
own LGU before acting. A guide to regulation that pretends to be authoritative is worse
than no guide.

## Why it's public

I wrote this from the regulatory side of the counter while planning my own setup, and the
information was scattered across sources that were half outdated, half unofficial, and
mostly written for people who already knew the answer. Consolidating it once means nobody
after me has to reassemble it.

## Scope

- **The Philippines.** LGU-level requirements vary; the guide flags where yours will.
- **Community pharmacy**, not hospital or manufacturing.
- **Not legal advice**, and not a substitute for the live FDA checklist.
