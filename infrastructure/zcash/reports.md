# Monthly Reports and Sustainability Notes (rolling page) — v0.1

## Purpose

This page is the rolling monthly record for operating the Zcash PeerTube instance: what we shipped, what broke (if anything), what it cost, what took time, and what we’re doing next.

Project hub (plan + tracker): [https://www.zkav.club/infrastructure/zcash/](https://www.zkav.club/infrastructure/zcash/)

How we publish: [https://www.zkav.club/infrastructure/zcash/publishing](https://www.zkav.club/infrastructure/zcash/publishing)

Moderation policy: [https://www.zkav.club/infrastructure/zcash/moderation](https://www.zkav.club/infrastructure/zcash/moderation)

## How this page works

* This is **one rolling page** (not one page per month).
* Each month has its own section (e.g., `## 2026-01`).
* Update the current month as work happens. At month end, add a short summary and start the next month.

## Pre-launch reporting (before the instance is live)

Until the instance is deployed, monthly reports still exist—but they report **project progress**, not runtime operations.

Rule of thumb:

* If it moved the project toward “instance live,” it belongs in the report (decisions, procurement, setup progress, tests, blockers).
* Runtime metrics that don’t exist yet should be marked **N/A (pre-launch)**.

Source of truth for status is the [Phase 5 tracker](https://www.zkav.club/infrastructure/zcash/#mvp-tracking-milestone-3) on the hub page; the monthly report captures *what changed this month and why*.

## Table of contents

* [2026-01](#2026-01)
* [2026-02](#2026-02)
* [2026-03](#2026-03)
* [2026-04](#2026-04)

---

## 2026-01

**Project status (pre-launch)**

* Phase 5 tracker link: [https://www.zkav.club/infrastructure/zcash/](https://www.zkav.club/infrastructure/zcash/)
* Summary: Published Milestone 1 plan as the canonical project hub page.

**Highlights**

* Published the PeerTube for Zcash Decision + Implementation Plan (Milestone 1).
* Established MVP posture: invite-only accounts, trusted uploader model, approval-first publishing.

**Milestone progress (pre-launch)**

* Decisions made:

  * Confirmed PeerTube as the deployment target for Zcash ecosystem video.
  * Defined curated federation posture and moderation baseline.
  * Defined initial channel ownership model (MVP: Zcash ecosystem groups; expansion planned later).
* Infra/provisioning progress: Not started (pre-launch).
* Workflow/policy progress: Plan published (Milestone 1).
* Testing completed: N/A (pre-launch).
* Blockers / risks:

  * Content + usage assumptions not yet published; sizing will be revisited once assumptions exist.

**New uploads (count + links)**

* N/A (pre-launch)

**Ops notes**

* Availability/uptime incidents: N/A (pre-launch)
* Backups status (last successful restore test date): N/A (pre-launch)
* Updates applied (PeerTube version, OS updates): N/A (pre-launch)

**Moderation notes**

* Reports received: N/A (pre-launch)
* Actions taken: N/A (pre-launch)
* Federation changes (date + action + reason): N/A (pre-launch)

**Costs**

* Hosting: $0 (pre-launch)
* Storage: $0 (pre-launch)
* Bandwidth: $0 (pre-launch)
* Other: $0 (pre-launch)

**Admin time**

* Hours (estimate): ~8 hours (full day: PeerTube research + instance/federation/moderation design + drafting/publishing Milestone 1)
* Main time sinks: PeerTube research (instances/federation/config), drafting the plan, and publishing the hub page

**Storage growth**

* GB/month: N/A (pre-launch)

**Risks / watch items**

* Ensure pre-launch assumptions and provisioning decisions land early in February.

**Next month focus**

* Publish content + usage assumptions.
* Start provisioning (domain/DNS, VPS, TLS, SMTP) and begin install.

---

## 2026-02

**Project status (pre-launch)**

* Phase 5 tracker link: [https://www.zkav.club/infrastructure/zcash/](https://www.zkav.club/infrastructure/zcash/)
* Summary: Turned the hub page into a living project tracker and published companion documentation (moderation, publishing, rolling reports) to support MVP operations.

**Highlights**

* Published companion docs:

  * Moderation policy: [https://www.zkav.club/infrastructure/zcash/moderation](https://www.zkav.club/infrastructure/zcash/moderation)
  * How we publish: [https://www.zkav.club/infrastructure/zcash/publishing](https://www.zkav.club/infrastructure/zcash/publishing)
  * Monthly reports (this page): [https://www.zkav.club/infrastructure/zcash/reports](https://www.zkav.club/infrastructure/zcash/reports)
* Refactored the hub page for readability (quick view + jump links) and upgraded Phase 5 into an operational tracker (cadence, evidence convention, sorted targets).
* Clarified privacy posture throughout (why PeerTube, no third‑party embeds on instance pages, and privacy notes in moderation/report handling).

**Milestone progress (pre-launch)**

* Decisions made:

  * Default publishing visibility: unlisted until approved, then public.
  * Reports are maintained as one rolling page (not one page per month).
  * Embed policy (MVP): no third-party video embeds on instance pages by default; PeerTube-hosted videos may be embedded elsewhere.
* Infra/provisioning progress: Not started (pre-launch).
* Workflow/policy progress:

  * Moderation policy published and corrected after a minor formatting issue on the live page.
  * Publishing workflow rewritten in plain language; added metadata examples, approval checklist, and corrections tiers.
* Testing completed: N/A (pre-launch).
* Blockers / risks:

  * Content + usage assumptions still pending (target publish date on hub: 2026-02-28).

**New uploads (count + links)**

* N/A (pre-launch)

**Ops notes**

* Availability/uptime incidents: N/A (pre-launch)
* Backups status (last successful restore test date): N/A (pre-launch)
* Updates applied (PeerTube version, OS updates): N/A (pre-launch)

**Moderation notes**

* Reports received: N/A (pre-launch)
* Actions taken: N/A (pre-launch)
* Federation changes (date + action + reason): N/A (pre-launch)

**Costs**

* Hosting: $0 (pre-launch)
* Storage: $0 (pre-launch)
* Bandwidth: $0 (pre-launch)
* Other: $0 (pre-launch)

**Admin time**

* Hours (estimate): ~8 hours (one full day: hub page revisions + companion docs + tracker/report structure)
* Main time sinks: hub page revisions, companion doc drafting, coordination meetings, and tracker/report structure

**Storage growth**

* GB/month: N/A (pre-launch)

**Risks / watch items**

* If assumptions slip past 2026-02-28, provisioning and sizing decisions may slip.

**Next month focus**

* Publish content + usage assumptions.
* Start provisioning (domain/DNS, VPS, TLS, SMTP) and begin install.
* Begin pilot workflow with 5–10 test uploads (unlisted) once the instance is live.

---

## 2026-03

(Template will be copied here at the start of the month.)

---

## 2026-04

(Template will be copied here at the start of the month.)
