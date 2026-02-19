# PeerTube for Zcash: Decision + Implementation Plan (v1)

**Executive summary (for publication):** Zk Av Club will deploy and operate a Zcash-focused [PeerTube](https://joinpeertube.org/) instance as a durable, community-run home for Zcash ecosystem video. This Milestone 1 document defines the MVP scope, hosting/deployment approach, federation posture, moderation baseline, and sustainability triggers needed to publish the plan by Jan 31, 2026. The MVP will run on a single VPS (local storage) using Docker Compose, with invite-only accounts, a trusted uploader list, and approval-first review for non-admin uploads. By Mar 31, 2026, the goal is a live MVP with backups + monitoring verified, curated federation implemented, seed content published, and the public “How we publish” + moderation policy posted.

Privacy note: today, if someone wants to watch a Zcon video, they generally have to do it on YouTube—meaning they’re tracked by Google unless they use extra tools and technical workarounds. A Zcash-run PeerTube instance gives the community a privacy-respecting default place to watch and share ecosystem video without requiring viewers to trade away their data.

**Owner:** Zk Av Club (Lead Organizer)

**Status:** Published (living document; initial release 2026-01-28)

**Last updated:** 2026-02-11

**Publication location:** [https://zkav.club/publishing-infrastructure/zcash/](https://zkav.club/publishing-infrastructure/zcash/)

**Project home:** This page is the main source of information for tracking the Zcash PeerTube project under Zk Av Club’s Community Media Infrastructure + Support service: [https://zkav.club/publishing-infrastructure](https://zkav.club/publishing-infrastructure)

**Grant proposal (context):** [https://forum.zcashcommunity.com/t/zcash-community-media-infrastructure-support-zk-av-club-2026/53913](https://forum.zcashcommunity.com/t/zcash-community-media-infrastructure-support-zk-av-club-2026/53913)

## Change log

* 2026-01-28: Published initial version.
* 2026-02-11: Updated published page (added companion doc links, Phase 5 tracker + cadence, channel ownership mechanics, operational log stubs, grant proposal link, and refreshed target dates).

Note: This is a living document. [Phase 5 tracking](#mvp-tracking-milestone-3) reflects current progress toward the MVP.

## Current status (quick view)

See Phase 5 for the full tracker.

Next up: publish content + usage assumptions by 2026-02-28, then provision the domain/VPS and begin install.

Current status last updated: 2026-02-11 (matches Phase 5 tracker).

* Public docs: Done (moderation, publishing, reports)
* Instance online (HTTPS): Not started
* Registration + roles: Not started
* Upload permissions + review workflow: Not started
* Backups + monitoring: Not started
* Curated federation posture: Not started
* Seed content (≥10 videos): Not started

Quick links:

* Moderation policy: [https://zkav.club/publishing-infrastructure/zcash/moderation](https://zkav.club/publishing-infrastructure/zcash/moderation)
* How we publish: [https://zkav.club/publishing-infrastructure/zcash/publishing](https://zkav.club/publishing-infrastructure/zcash/publishing)
* Monthly reports: [https://zkav.club/publishing-infrastructure/zcash/reports](https://zkav.club/publishing-infrastructure/zcash/reports)

Jump to:

* [Context + deliverable (Section 0)](#0-context-and-deliverable)
* [Goals + scope (Section 1)](#1-goals-scope-and-non-goals)
* [Decisions (Section 2)](#2-decisions-mvp)
* [Assumptions (Section 3)](#3-requirements-checklist-pre-provisioning)
* [Channel governance (Phase 1)](#initial-channel-taxonomy-mvp)
* [Provisioning checklist (Phase 2)](#phase-2--provision--install)
* [MVP tracker (Phase 5)](#mvp-tracking-milestone-3)
* [Operational logs (Phase 6)](#operational-logs-mvp-stubs)
* [Sustainability notes (Section 6)](#6-sustainability-notes-publish-up-front)

Where things live:

* Policy: [https://zkav.club/publishing-infrastructure/zcash/moderation](https://zkav.club/publishing-infrastructure/zcash/moderation)
* Workflow: [https://zkav.club/publishing-infrastructure/zcash/publishing](https://zkav.club/publishing-infrastructure/zcash/publishing)
* Ops history (rolling): [https://zkav.club/publishing-infrastructure/zcash/reports](https://zkav.club/publishing-infrastructure/zcash/reports)
* This hub: decisions + tracking

---

## 0) Context and deliverable

This page is the canonical tracker for deploying and operating a Zcash-focused PeerTube instance with clear moderation, publishing workflow, and sustainability reporting.

Milestone 1 deliverable: publish this plan publicly (scope, hosting approach, moderation baseline, sustainability notes).

---

## 1) Goals, scope, and non-goals

### Goals (what success looks like)

1. A stable PeerTube “home” for Zcash ecosystem videos that reduces dependence on centralized platforms.
2. A privacy-respecting default way to watch and share Zcash ecosystem video without requiring viewers to accept surveillance advertising ecosystems.
3. A repeatable publishing workflow aligned with PeerTube’s capabilities and a clear internal publication process.
4. Clear moderation + governance baseline that is easy to explain and enforce.
5. Sustainability notes (costs, bandwidth, admin hours, scaling assumptions) tracked monthly.

### Scope (Phase 1 / MVP)

* One PeerTube instance (Zcash branded), operated with a privacy-respecting viewer experience (no requirement to log in to watch; no reliance on ad-tech tracking to access content).
* Admin + moderator roles, minimal channel structure, upload/transcode enabled (with guardrails).
* Federation enabled with an explicit policy.
* Backup + monitoring + update routine defined and tested.
* Initial seed uploads (start with a small curated set, then ramp).

### Non-goals (Phase 1)

* “Open upload for everyone on the internet” on day one.
* Complex multi-tenant architecture.
* Custom plugin development (unless clearly required later).

---

## 2) Decisions (MVP)

### 0) Instance identity (DECIDED)

* Decision: this will be a PeerTube instance for Zcash.
* Implications: branding, channel taxonomy, moderation policy scope, and seed content are Zcash-ecosystem focused.

### A) Hosting approach (DECISION)

* Decision (MVP): Option 1 — Single VPS with local storage.
* Privacy note: operating our own instance gives the community an alternative to platform surveillance defaults (e.g., YouTube/Google tracking) and reduces dependency on third-party tracking infrastructure.
* Rationale: fastest path to a stable MVP; easiest to operate while learning real usage patterns.
* Migration posture: structure storage + backups so media can move to object storage later if needed.

### B) Install method (DECISION)

* Decision (MVP): Docker Compose on the VPS.
* Rationale: repeatable deployment, easier upgrades/rollbacks, easier to document for replication.

### C) Federation posture (DECISION)

* Decision (MVP): Curated federation (explicit allow/block policy).
* Rationale: reduces moderation surprise-load during launch; easier to explain publicly.

### D) Accounts, uploads, and review (DECISION)

* Registration (MVP): Invite-only accounts.
* Privacy note: invite-only accounts reduce spam/abuse risk and also reduce incentives to deploy invasive anti-spam tracking; viewers should not need an account to watch published videos.
* Who can upload (MVP): Trusted uploader list (admins + explicitly approved accounts).
* Review model (MVP): Approval-first for non-admin uploads (auto-block/unlisted until approved).

### E) What “published” means (DECISION)

* Decision (MVP): a video is “published” when it is public, has required metadata, and has passed any required review.

---

## 3) Requirements checklist (pre-provisioning)

### Content + usage assumptions (planned)

We will publish initial content and usage assumptions in February 2026 (in progress). Target publish date: 2026-02-28.

Assumptions will cover:

* Expected library size in the first 3 months (uploads, average file size)
* Expected peak viewing patterns (e.g., launch week, event drops)
* Validation of the MVP operating model (invite-only accounts, trusted uploaders, approval-first)

Until these assumptions are published, we will provision for conservative MVP load and revisit sizing once we have real usage data.

These assumptions will be used to validate the capacity baseline and to set/adjust sustainability triggers.

### Capacity baseline

Start above “minimums” if transcoding will run on-instance. Plan for growth in CPU, storage, and upload bandwidth.

Privacy note: prioritize operational choices that keep viewing simple and private (e.g., avoid third-party embeds and unnecessary analytics that introduce cross-site tracking).

---

## 4) Moderation policy (summary)

This section is a short operational summary. The full public policy lives here:

* Moderation policy: [https://zkav.club/publishing-infrastructure/zcash/moderation](https://zkav.club/publishing-infrastructure/zcash/moderation)

MVP summary:

* Roles: admins (instance policy + infra) and moderators (reports + enforcement).
* Reporting targets: illegal/urgent same day; other reports within 72 hours.
* Upload gating: approval-first for non-admin uploads.
* Federation: curated posture with actions logged.
* Privacy posture: handle reports as sensitive; avoid publishing personal identifiers.

---

## 5) Deployment plan (build → launch → operate)

### Phase 1 — Research & design (publishable outputs)

* Hosting decision + rationale
* Federation posture + rationale
* Moderation baseline + roles
* Initial channel taxonomy (finalized list + channel owners)
* Upload policy (who can upload; approval-first)

#### Initial channel taxonomy (MVP)

During the MVP, channels are owned by Zcash ecosystem groups. Zk Av Club admins create channels and manage instance-level policy, while channel owners manage what gets published in their channel and ensure metadata quality.

Channel ownership mechanics (MVP):

* Admins control: channel creation, instance-wide settings, federation posture, account provisioning, and final escalation.
* Channel owners control: channel direction, approval to publish, and who is authorized as a trusted uploader for that channel.
* Uploader access: granted per-channel, by admins, based on a written request from the channel owner (name/handle + scope of access).
* Change control: channel owner requests to add/remove uploaders; admins execute changes and keep a lightweight access log.
* Historic Zcon exception: Zk Av Club admins upload and manage metadata for historic Zcon videos during MVP, in coordination with the Zcash Foundation.

**Initial channels (MVP launch):**

* Zcash Foundation — Zcon (historic + new)

  * Channel owner: Zcash Foundation
  * Uploader access: Zk Av Club admins (historic Zcon) + any ZF-designated trusted uploader(s) approved by admins
  * During the MVP, Zk Av Club admins will upload and manage metadata for historic Zcon videos (in coordination with Zcash Foundation).
* ZecHub

  * Channel owner: ZecHub
  * Uploader access: ZecHub-designated trusted uploader(s) approved by admins
  * This channel will hold ZecHub programming (and other approved ecosystem content unless/until additional channels are created late MVP).

**Planned expansion (late MVP):**
Toward the end of the MVP, we will create additional channels for other selected organizations and communities in the Zcash ecosystem. Channel additions will be based on readiness (trusted uploader identified, moderation expectations agreed, and metadata standards understood).

Notes:

* Channels are created by admins only during MVP.
* We will revisit channel structure after February 2026 usage assumptions are published.

### Phase 2 — Provision & install

#### Infrastructure checklist

* Domain + DNS
* Privacy posture: avoid third-party trackers/embeds on the instance; keep logs and analytics minimal and purpose-limited
* Embed policy (MVP): no third-party video embeds on instance pages by default (e.g., YouTube/Vimeo embeds). Link out instead if needed to avoid reintroducing third-party tracking on instance pages. This does not restrict embedding PeerTube-hosted videos on other websites, forums, or chats.
* TLS (HTTPS)
* SMTP (account emails, moderation notifications)
* Backup target (encrypted)
* Monitoring (uptime + disk + CPU)
* Update cadence

#### PeerTube install

* Deploy via Docker Compose
* Configure instance settings via admin UI (ensure config is tracked)

### Phase 3 — Configure + harden

* Registration mode: invite-only
* Default video visibility: unlisted until approved (then set to public)
* Privacy posture: viewers can watch public videos without creating an account; avoid third-party tracking scripts; keep operational logging minimal and purpose-limited
* Transcoding settings (start conservative)
* Federation allow/block approach implemented
* Abuse/report workflow tested end-to-end

### Phase 4 — Pilot publishing workflow

This section is a short operational summary. The full public workflow lives here:

* How we publish: [https://zkav.club/publishing-infrastructure/zcash/publishing](https://zkav.club/publishing-infrastructure/zcash/publishing)

Pilot tasks (MVP):

* Upload 5–10 test videos (unlisted)
* Validate playback, metadata conventions, captions flow (if used), and federation behavior
* Run the review/approval flow end-to-end
* Publish at least one video to confirm the public path and logging into monthly reports

### Phase 5 — MVP launch

This tracker is the source of truth for project status.

Milestone 3 exit criteria: Milestone 3 is complete when all rows in the Phase 5 tracker are marked Done (or Deferred with a brief rationale and a new target date in Notes).

#### MVP tracking (Milestone 3)

Update this block as work progresses. Status values: Not started / In progress / Done / Blocked.

Update cadence: weekly (or after major milestones). If the tracker isn’t updated for more than 7 days, treat statuses as stale.

Targets are best-effort. If a target slips, update the row with a new date and a brief rationale in Notes.

Last tracker update: 2026-02-11

When marking an item Done, add a short note (and optionally a link) in Notes.

| Area       | Item                                                                 | Owner                              | Target date | Status      | Notes / links                                                                                                  |
| ---------- | -------------------------------------------------------------------- | ---------------------------------- | ----------- | ----------- | -------------------------------------------------------------------------------------------------------------- |
| Docs       | Moderation policy published                                          | Zk Av Club                         | 2026-02-11  | Done        | [https://zkav.club/publishing-infrastructure/zcash/moderation](https://zkav.club/publishing-infrastructure/zcash/moderation) |
| Docs       | How we publish published                                             | Zk Av Club                         | 2026-02-11  | Done        | [https://zkav.club/publishing-infrastructure/zcash/publishing](https://zkav.club/publishing-infrastructure/zcash/publishing) |
| Docs       | Monthly reports & sustainability notes published                     | Zk Av Club                         | 2026-02-11  | Done        | [https://zkav.club/publishing-infrastructure/zcash/reports](https://zkav.club/publishing-infrastructure/zcash/reports)       |
| Planning   | Publish content + usage assumptions                                  | Zk Av Club admins                  | 2026-02-28  | Not started | Publish on hub Section 3 + link here when live                                                                 |
| Infra      | Instance publicly reachable over HTTPS                               | Zk Av Club admins                  | 2026-03-07  | Not started |                                                                                                                |
| Access     | Registration mode set to invite-only                                 | Zk Av Club admins                  | 2026-03-07  | Not started |                                                                                                                |
| Roles      | Roles assigned (admins + moderators) and tested                      | Zk Av Club admins                  | 2026-03-07  | Not started |                                                                                                                |
| Uploads    | Upload permissions configured (trusted uploader list, per-channel)   | Zk Av Club admins + channel owners | 2026-03-14  | Not started |                                                                                                                |
| Workflow   | Review/approval workflow works end-to-end                            | Zk Av Club admins + moderators     | 2026-03-14  | Not started |                                                                                                                |
| Infra      | Monitoring enabled (uptime + CPU + disk) with basic alerts           | Zk Av Club admins                  | 2026-03-14  | Not started |                                                                                                                |
| Infra      | Backups configured and restore test performed                        | Zk Av Club admins                  | 2026-03-14  | Not started |                                                                                                                |
| Federation | Curated federation posture implemented (allow/block; changes logged) | Zk Av Club admins + moderators     | 2026-03-21  | Not started |                                                                                                                |
| Content    | Seed set published (≥10 videos) with required metadata               | Zk Av Club admins + channel owners | 2026-03-28  | Not started |                                                                                                                |

Milestone 3 is complete when all non-doc items above are marked Done (or explicitly deferred with rationale).

### Phase 6 — Operate & iterate (monthly)

Monthly reports will be maintained as one rolling page at [https://zkav.club/publishing-infrastructure/zcash/reports](https://zkav.club/publishing-infrastructure/zcash/reports).

#### Operational logs (MVP stubs)

These logs support accountability for curated federation and per-channel uploader access during MVP.

Uploader access log (MVP)

| Date | Channel | Change | Requested by (channel owner) | Executed by (admin) | Notes |
| ---- | ------- | ------ | ---------------------------- | ------------------- | ----- |
|      |         |        |                              |                     |       |

Federation log (MVP)

| Date | Instance | Action (allow/block/unfollow) | Reason | Decided by | Notes |
| ---- | -------- | ----------------------------- | ------ | ---------- | ----- |
|      |          |                               |        |            |       |

Grant-aligned reporting metrics:

* Upload count + links
* Privacy notes (if relevant): any changes that affect viewer privacy posture (e.g., analytics/logging changes, embed policies)
* Hosting/bandwidth costs
* Admin hours

Recommended additions:

* Storage growth (GB/month)
* Moderation load (reports/week)

---

## 6) Sustainability notes (publish up front)

### Main cost drivers

* Storage growth
* Outbound bandwidth spikes
* Transcoding compute

Privacy tradeoff: reducing reliance on surveillance platforms may increase our direct hosting and bandwidth responsibility. We treat this as a worthwhile tradeoff for a privacy-respecting default.

### Sustainability plan (MVP)

* Start with conservative upload permissions (invite-only + trusted uploaders).
* Define scale triggers (initial values; revise after 30–60 days of real data):

  * Disk usage > 70% (sustained for 7 days)
  * Bandwidth costs > $200/month (for 2 consecutive months)
  * Moderation queue > 10 reports/week (for 2 consecutive weeks)
  * Admin time > 10 hours/week (sustained for 4 weeks)
* If triggers hit: consider object storage, tighter federation, reduced intake, or adding moderator/admin capacity.

### Replication notes (if sustainable)

If ops is stable post-MVP, publish:

* Replication guide (install + config + moderation defaults)
* Minimal instance checklist for sister instances

## 7) Timeline aligned to grant milestones

* By Jan 31, 2026: publish this plan (Milestone 1).
* By Mar 31, 2026: PeerTube MVP live, or publish deferral plan with reasons + new date (Milestone 3).

See Phase 5 tracker for current targets; dates there are authoritative.

---

## 8) Milestone 1 completion record

Milestone 1 is complete when the plan includes the items below. This section is kept as a record for grant tracking.

**Milestone 1 completion date:** 2026-01-28

**Milestone 1 artifact (published):** [https://zkav.club/publishing-infrastructure/zcash/](https://zkav.club/publishing-infrastructure/zcash/)

Checklist (Milestone 1):

* Scope statement (what MVP is / isn’t)
* Hosting decision + rationale
* Install method
* Moderation baseline (roles, reports, approval-first, federation posture)
* Sustainability notes + monthly reporting plan
* Timeline to MVP through Mar 31, 2026
