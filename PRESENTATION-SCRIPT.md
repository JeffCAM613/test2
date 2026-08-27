# Kortex — Team Walkthrough Script

For walking your own team through the CoE submission **before** it goes to the CoE. The goal
of that meeting is not to admire the document — it is to get the team to own it, correct
what is wrong, and decide the open questions.

## How to use this

Each section gives you three things:

- **Say this** — the substance, in your voice. Not a script to read aloud; the points to land.
- **Provenance** — where each claim came from, so you can be straight with the team about
  what they wrote and what was drafted for them.
- **Decide** — what the team actually needs to settle before this goes out.

### Provenance key

| | Meaning |
|---|---|
| 🟢 **OURS** | From our repository, docs, or something the team already said. Not invented. |
| 🟡 **REFRAMED** | Our material, rewritten for a business audience. Substance ours, words new. |
| 🔴 **ADDED** | Proposed during drafting. **Not previously our position.** Needs adoption or removal. |

**The honest headline for your team:** the *facts* are almost all ours. The *framing* — turning
an engineering project into a business case — is new, because our repository contains no
business-value language at all. One sentence in the root README about "boosting team
productivity" is the whole of it. Everything in Section 2 is built on top of that.

---

## Before you start — 2 minutes of framing

> "This is the document we send the AI CoE. Before it goes anywhere I want us to agree it
> says what we actually mean, because it commits us to some things.
>
> Two things to know going in. First, we're doing what the policy asks — reach out before
> you build. We're not asking forgiveness for something already running. Second, our
> development is blocked on GitHub Models being retired, and the CoE is the group that can
> unblock it. So this is partly a submission and partly an ask.
>
> As we go, I'll flag anything in here that we haven't actually said before, so you know
> what we'd be signing up to."

**Why open this way:** it sets the meeting up as a review rather than a presentation, and it
tells people their corrections are wanted. You will get better input.

---

## Section 1 — Executive summary

**Say this.** Kortex is an internal platform for the KTP Suite. Not a chatbot — an
alternative entry point for our daily work: see what needs attention, ask what a product
does, look up a case, and act on it. We're at early development. We're blocked on the model
service. We're asking the CoE for three things: a sanctioned model service, confirmation
that our data handling is acceptable, and agreement on what has to be true before anyone
outside the pilot uses it.

**Provenance**

| Claim | |
|---|---|
| Product family — CTI, KTP, FFC, Payment Factory, KTPWeb, Cargo | 🟢 From our orchestrator prompt |
| "Entry point for daily work, not a Q&A assistant" | 🟢 Our own framing, this week |
| Early development stage; GitHub Models retired | 🟢 Fact |
| The four figures (7 use cases, 8 agents, 2 state-changing capabilities, 1 content egress) | 🟡 Counted from our own material |
| "Three reasons we're presenting now" — ask before building, avoid duplicate effort, standards designed in | 🔴 **ADDED.** Written to mirror the CoE's own charter language back at them. |
| "We are not asking for production approval" | 🔴 **ADDED.** A deliberate strategy — see Decide. |

**Decide**

1. **Are we comfortable asking for less than approval?** The recommendation is to ask for
   endorsement in principle plus D-1, not production sign-off. Narrow asks get granted;
   broad ones get deferred pending more information. If the team wants to push for more,
   that is a real choice — but the likely outcome is a longer wait.
2. **Is "entry point for daily work" the description we want on record?** It is more
   ambitious than "assistant" and it raises the governance bar. It is also the truth.

---

## Section 2 — Objectives and business value

**Say this.** Four objectives, and they divide by the kind of question being asked.
**One** — product knowledge: how does this work, for the version I'm actually running.
**Two** — resolution: something is broken, get me from symptom to fix, covering both
application errors and vulnerabilities. **Three** — one place to start the day, across Jira,
Salesforce, ServiceNow and the databases. **Four** — build AI development skills in the team.
Pilot population is DevOps and Client Services.

> **Note on the restructure.** An earlier draft split these differently and the first two
> objectives overlapped — both were essentially "finding things is slow." The current split
> is by *question type*: **"how does this work?"** versus **"this is broken."** Users
> recognise that division because it is how they experience the work, and it lets Objective 2
> cover troubleshooting and CVEs together rather than treating vulnerabilities as special.

**Provenance**

| Claim | |
|---|---|
| The four audience profiles — Support / Consultants and PMs / DevOps and SRE / Management | 🟢 **Verbatim from our own agent prompt.** We wrote this; it was just never surfaced. |
| Pilot = DevOps and Client Services | 🟢 Ours |
| Objective 1 — SME dependency, 24/7 availability, version-aware answers | 🟢 Ours |
| Objective 1 — onboarding benefit, and answers being auditable | 🔴 **ADDED.** Both are real and neither had been articulated. |
| Objective 2 — days of exploration before minutes of fixing | 🟢 Your example. 🟡 in wording only. |
| Objective 2 — vulnerability process and knowledge reuse | 🟢 Your description of how it actually works |
| Objective 3 — one place to start the day | 🟡 **Reframed.** Previously "connect AI to the systems we use," which described plumbing as though it were a benefit. Nobody wants an integration; they want to not check five tools before starting. |
| Objective 4 — build AI development skills | 🟡 **Reframed.** Our README says *"Learn and demonstrate the LangChain framework end-to-end."* Generalised to skills and optionality, because the original reads in a review room as "we wanted to learn a library." |
| "We have no measured baseline and won't quote estimates as evidence" | 🔴 **ADDED** |
| The four-week baseline proposal | 🔴 **ADDED** |

> ### ⚠️ One claim to be careful with
>
> The document says documentation is **"uploaded as it is published, and on each release"** —
> an operational commitment we control. It deliberately does **not** say the corpus is
> "always up to date," because that is a property of the system and we cannot currently
> guarantee it.
>
> The gap: documents are deduplicated by content hash, which stops the *same* file being
> ingested twice, but nothing removes a **superseded revision**. Keeping older *versions* is
> correct and deliberate — colleagues on 23.2 need 23.2's answer. The problem is a *corrected*
> document: publish a fix to the 24.1 guide, ingest it, and both the old and new copies now
> sit in the corpus, either of which retrieval may surface. Since version-correct answers are
> the strongest thing we claim, this needs closing. It is on the engineering list.

> ⚠️ **Flag this one explicitly to the team.** An earlier draft claimed CVE assessment was
> "a manual cross-reference between the advisory and the library inventory." That was wrong —
> it was inferred, not sourced. The real process is: report arrives, distributed, each person
> investigates their own case or server, findings written up. **The correction made the case
> stronger**, because it shifts the value from version-matching to reusing our own resolution
> history — which is something no off-the-shelf tool can do.

**Decide**

1. **We need numbers.** Not one figure appears in this section. Rough is fine — order of
   magnitude beats absence. Five would transform it: pilot headcount; supported product
   versions; CVEs per month or quarter; typical elapsed time to assess one; corpus size.
2. **One concrete example.** "We spent N days on issue X before finding a colleague had
   documented it months earlier." A single verifiable instance outperforms two paragraphs of
   characterisation — and it is the thing a reviewer remembers.
3. **Does the team accept the business framing at all?** This is the section most changed
   from what we actually wrote down.

---

## Section 3 — Use cases

**Say this.** Seven use cases, all within Kortex. Some are delivered through skills — the
integrations our agents call. Statuses are honest: two working, one planned, four partial.

**Provenance**

| Claim | |
|---|---|
| All seven use cases | 🟢 Every one maps to a real story (K0001–K0006) or a real component |
| Statuses | 🟢 Confirmed by us |
| UC-01…UC-07 numbering, "primary users" column | 🔴 **ADDED** packaging. Our identifiers are K-numbers. |
| Image input planned, held pending the model decision | 🟢 Ours |
| Hosted search rejected — usage limits *and* third-party query history | 🟢 Both reasons confirmed by us |

> ⚠️ **Correction worth mentioning.** An earlier draft labelled Case 360° and the instruction
> profiles as a "separate track." Wrong — they are layers of the same system, and the skills
> are the integration layer our agents call. That correction matters because it means
> Salesforce and ServiceNow content flows *through Kortex*, which is exactly why Section 7
> reads the way it does now.

> ### The agent count grew
>
> The paper now describes **eight agents, two of them working**. Five of the six planned ones
> already exist as skills built during the proof of concept — Salesforce, Jira, ServiceNow,
> Infrastructure and Reports — and are being converted so the orchestrator can route to them
> directly. There is a full register in the appendix with a client-data column.
>
> Two facts in that register will draw questions, so know them going in: **four of the eight
> reach systems holding client-identifying content**, and the **Reports agent inherits the
> classification of whatever it renders** — a branded PDF built from case data carries that
> data out of the platform as a file.

**Decide**

1. **Is "partial" right for UC-04 through UC-07?** Four things marked partial invites the
   question "so what actually works?" If any is closer to done, say so.
2. **Should UC-06 (Case 360°) be in this submission at all**, given it is the one that brings
   client-identifying content into scope? Including it is honest. Excluding it makes the
   submission simpler and requires a second one later.

---

## Section 4 — Where the project stands

**Say this.** Be direct: the core pattern works end to end, the multi-agent layer is written
but unvalidated, and development is stopped because GitHub Models was retired. It is a
procurement problem, not an engineering one — our client is OpenAI-compatible, so any
sanctioned provider is a config change. And it now costs money, which it did not before.

**Provenance**

| Claim | |
|---|---|
| The blocker, and what still works | 🟢 Ours |
| "GitHub Models was an experimentation tier; we'd have had to move regardless" | 🟡 The **evidence is ours** — our June status report records ~60s first responses from rate-limit backoff, and our ingest config carries a deliberate 5-second pause between embedding batches. The **argument** was drafted. |
| Provider options table | 🔴 **ADDED** |
| "No longer zero marginal cost" | 🔴 **ADDED** — and it corrects an earlier draft that claimed the Copilot entitlement made this free. That is no longer true. |
| "Embedded once, not per query; cheap model for classification and grading" | 🟢 True of our design |

**Decide**

1. **Do we state a provider preference, or leave it fully open?** The document currently
   says we have no preference we would defend over theirs. That is honest and it invites
   them to solve it — which is the point. Some teams prefer to arrive with a recommendation.
2. **Who owns the running cost?** D-1 now asks this. If we have a view on where the budget
   sits, better to say it than be asked.

---

## Section 5 — Solution architecture

**Say this.** Three tiers, containerised, everything self-hosted except what has to leave.
The important part is not the tier diagram — it is the trust boundary. Three things cross it:
sign-in, model inference, and CVE lookups. Plus search terms indirectly.

**Provenance**

| Claim | |
|---|---|
| Tiers, request path, agent structure | 🟢 From our architecture docs and code |
| **The trust-boundary framing** | 🔴 **ADDED.** Our own docs have a "Security Model" table but never analyse data egress. This is the single most useful reframing in the paper for this audience. |
| Search egress detail — five engines, corporate proxy, no vendor account | 🟢 Ours |

> ### On the architecture diagram
>
> It now shows **three zones**, not one boundary, and the distinction is worth spelling out
> in the room. The agents reach outward into **Finastra's own systems** — Salesforce,
> ServiceNow, Jira, Office 365 — but that is not disclosure: the data is ours before Kortex
> touches it, and reading it reveals nothing to anyone new. Disclosure happens only in the
> third zone, and that list is short — the model provider, the public vulnerability
> database, and the search engines.
>
> Being able to say *"most of what looks like egress isn't"* is a strong position, and it
> only reads that way if the diagram separates the two.

**Decide**

1. **Two things are missing and a reviewer will ask.** The diagram does not show **how
   documents get into the corpus** — the ingestion path — and the document never says **where
   this runs**: which environment, which network zone, who administers the hosts. Both should
   be added before it goes out.

---

## Section 6 — Technical components

**Say this.** Everything chosen for portability, and anything holding Finastra data is
self-hosted. Where we rejected a hosted option, the reason is recorded.

**Provenance.** 🟢 The component list is entirely ours — from our dependency files, compose
file and code. 🟡 The rationale column is drafted; the *choices* are ours, the *justifications*
are written for this audience.

**Decide.** Nothing blocking. Confirm the rationale column reflects why we actually chose
each thing, rather than a plausible reason invented after the fact.

---

## Section 7 — Protecting company and client data

**This is the section to spend the most time on. It contains the most that is new, and it
commits us to things.**

**Say this.** The CoE's job includes making sure AI solutions meet the standards our
customers expect. Because we are presenting before building, we can design that in. Here is
what data we touch, what leaves, where we can act rather than just answer, and what we
propose to do about each.

**Provenance**

| Claim | |
|---|---|
| Admin review before documents are indexed | 🟢 Ours |
| Database write capability and how privileges work | 🟢 Ours |
| Server remediation as a planned direction | 🟢 Ours |
| Self-hosted stores, 24h chat expiry, SOPS secrets, deny-by-default RBAC | 🟢 Ours, already built |
| **"Client data is never ingested into the corpus"** | 🔴 **ADDED — and this is the big one.** See below. |
| The corpus-vs-transient distinction | 🔴 **ADDED** |
| Four controls on retrieved case content | 🔴 **ADDED** |
| **Entitlement pass-through** — use the user's own permissions, not a service account | 🔴 **ADDED** |
| Web search interlock | 🟡 **Your idea.** The mechanism — deterministic state flag rather than model judgment — was drafted. |
| The six-row risk and strategy table | 🔴 **ADDED** |
| Regulatory questions | 🔴 **ADDED** |

> ### ⚠️ The one thing to put to the team explicitly
>
> **"Client data is never ingested into the corpus" is not an existing policy. We would be
> creating it in this document.**
>
> It is the right constraint and it is the strongest claim in the paper — but the team has to
> actually agree to hold it, because it will be tested the moment Case 360° lands. Ask
> directly: *are we committing to this?*
>
> If yes, it needs writing down as a real policy, not just as a sentence in a submission.
> If the team is not prepared to hold it, the wording has to change **before** the paper goes
> out, not after.

**Explaining the corpus-vs-transient point** — the team will need this, it is the conceptual
core of the section:

> There are two completely different ways data can be "in" Kortex.
>
> **One:** someone uploads a document. It gets cut into fragments, filed permanently, and
> anyone with chat access can surface it — and won't know they did, because retrieval is
> silent. The whole thing went to the model provider to be indexed. It stays until deleted.
>
> **Two:** Kortex fetches something for you right now — a specific Salesforce case — uses it
> to answer, and it's gone. Nothing filed, nothing searchable, nobody else can reach it.
>
> The first is the risky one. So "no client data in the corpus" means *never the first*.
> Saying "no client data anywhere in Kortex" would also forbid the second — which makes
> Case 360° impossible, and Case 360° is a large part of the point.

**Decide**

1. **Do we commit to "never in the corpus"?** (above)
2. **Entitlement pass-through — do we build it?** When Kortex fetches a Salesforce case,
   does it use *the requester's* permissions or a service account's? If a service account,
   Kortex becomes a way to read cases a person could not open directly. Easy to miss because
   reading feels less consequential than writing. It is not.
3. **Read-only Phase 1 for database operations?** The recommendation is to present read-only
   for this approval and bring write back as its own decision with its own controls. That
   lets the rest through quickly. The counter-argument is that it delays something we already
   have working.
4. **Do we keep server remediation in the document?** It is drafted in. It is also the single
   largest escalation in the paper and will attract the hardest questions — before our
   foundations are approved. Three options: keep it, remove it, or state it as a direction
   that returns as its own decision (which is roughly how it reads now).
5. **How good is the anonymisation** in the test databases? "Anonymised" carries weight the
   word does not always earn — data that can be re-identified is *pseudonymised*, and still
   personal data. Worth knowing before being asked.

---

## Section 8 — Security, compliance and governance

**Say this.** Here is what is built and working, and here is what has to change before anyone
outside the pilot uses it. Including the things that are not flattering.

**Provenance**

| Claim | |
|---|---|
| Controls in place — OIDC, RBAC, security headers, SOPS, non-root containers | 🟢 Ours, real |
| The TLS "development exception" | 🟢 Ours — **our own code comment already records the fix**. We are naming it, not confessing it. |
| "No automated tests, no CI security gates" | 🟢 Fact |
| Supply chain marked partial | 🟢 **Our own OWASP assessment says this** |
| The "required before wider use" column | 🔴 **ADDED** |

**Decide**

1. **Are we comfortable being this candid?** The recommendation is strongly yes — presenting
   our own gaps first moves a reviewer from auditor to advisor, and everything here is
   discoverable anyway. But the team should choose it deliberately rather than discover it
   in the room.
2. **The biggest gap is no tests.** It matters more than any individual finding, because
   every control we claim is currently an assertion rather than something we can demonstrate.
   Worth saying we know that.
3. **Should we add an OWASP LLM Top 10 mapping?** Our security doc maps to the *web* Top 10.
   A CoE reviewing an AI system will expect the LLM-specific one — prompt injection, excessive
   agency, sensitive information disclosure. Adding it closes most of the AI-specific gaps at
   once and reads as maturity rather than catch-up.

---

## Section 9 — Roadmap and next steps

**Say this.** Three architectural iterations so far, each fixing a limitation of the last.
Now blocked. After the blocker: design decisions, hardening, evidence, operational readiness
— and we propose the last two are gates, not parallel work.

**Provenance.** 🟢 The v1.0 → v1.1 → v1.2 progression is entirely ours and it is genuinely
well documented — each release records *why* it was needed. Most teams cannot explain their
own architecture's history; we can, in writing. 🔴 The gates are added.

**Decide**

1. **Do we propose the gate ourselves, or let them set it?** Proposing it looks like
   ownership. It also means we are held to it. The document currently proposes it and invites
   them to adjust.
2. **Who owns this in production?** Right now: nobody — it is a team project on Compose.
   This is the question that most often stalls initiatives like ours. Far better raised by us
   than by them.

---

## Section 10 — Decisions requested

**Say this.** Seven decisions, in the order they block us. D-1 is the immediate one.

**Provenance.** 🔴 **ADDED, all of it.** Nothing like this existed. It is what turns the paper
from a status report into something a review board can act on.

**Decide.** Are these the right seven, in the right order? In particular — D-3 asks them
outright whether this duplicates something Finastra already has. That is a slightly risky
question, because the answer might be yes for documentation Q&A. It is also exactly what
their charter says they are for, and asking it first is better than being told.

---

## Closing the meeting

Land these four:

1. **Do we adopt the "client data never in the corpus" commitment?**
2. **Read-only Phase 1 for database operations — yes or no?**
3. **Does server remediation stay in the document?**
4. **Who is getting me the numbers, and by when?**

Then: *"I'll fold in the corrections and send it round before it goes to the CoE."*

---

## Questions your team will probably ask

**"Why are we admitting to all these gaps?"**
Because they are discoverable, and a reviewer who finds one thing we did not disclose
re-checks everything else. Volunteering them costs us little and buys credibility we cannot
purchase otherwise. Presenting our own risk register moves them from auditor to advisor.

**"Isn't this too honest about how early we are?"**
The alternative is claiming maturity we do not have, and then being asked for the test
results. Early-stage is a fine thing to be when you are doing exactly what the policy asks.

**"What if they say use M365 Copilot instead?"**
Concede the half that is true — plain documentation Q&A probably *could* be served by a
general assistant. Then hold the half that is not: CVE assessment against our own resolution
history, and the operational actions. No off-the-shelf product has our history or reaches our
systems. Conceding the weak half is what makes the strong half credible.

**"What if they say no to the database write capability?"**
Then we build read-only first, which is most of the value anyway, and come back. That is why
the phasing option is in there — it gives them something to say yes to.

**"Are we committing to things we can't deliver?"**
That is precisely what this meeting is for. Every 🔴 item is a proposal, not a promise, until
the team adopts it.
