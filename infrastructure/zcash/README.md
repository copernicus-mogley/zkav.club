# PeerTube for Zcash: Decision + Implementation Plan (v1)

**Executive summary (for publication):** Zk Av Club will deploy and operate a Zcash-focused PeerTube instance as a durable, community-run home for Zcash ecosystem video. This Milestone 1 document defines the MVP scope, hosting/deployment approach, federation posture, moderation baseline, and sustainability triggers needed to publish the plan by Jan 31, 2026. The MVP will run on a single VPS (local storage) using Docker Compose, with invite-only accounts, a trusted uploader list, and approval-first review for non-admin uploads. By Mar 31, 2026, the goal is a live MVP with backups + monitoring verified, curated federation implemented, seed content published, and the public “How we publish” + moderation policy posted.

**Owner:** Zk Av Club (Lead Organizer)

**Status:** Published (initial release 2026-01-28; updates in progress)

**Last updated:** 2026-02-11

**Publication location:** [https://www.zkav.club/infrastructure/zcash/](https://www.zkav.club/infrastructure/zcash/)

**Project home:** This page is the main source of information for tracking the Zcash PeerTube project under Zk Av Club’s Community Media Infrastructure + Support service: [https://www.zkav.club/infrastructure](https://www.zkav.club/infrastructure)

**Grant proposal (context):** [https://forum.zcashcommunity.com/t/zcash-community-media-infrastructure-support-zk-av-club-2026/53913](https://forum.zcashcommunity.com/t/zcash-community-media-infrastructure-support-zk-av-club-2026/53913)

## Change log

* 2026-01-28: Published initial version.
* 2026-02-11: Began updates (governance/channel ownership clarified; publication metadata updated).

Note: This is a living document. Phase 5 tracking reflects current progress toward the MVP.

## Current status (quick view)

See Phase 5 for the full tracker.

* Public docs: Done (moderation, publishing, reports)
* Instance online (HTTPS): Not started
* Registration + roles: Not started
* Upload permissions + review workflow: Not started
* Backups + monitoring: Not started
* Curated federation posture: Not started
* Seed content (≥10 videos): Not started

Quick links:

* Moderation policy: [https://www.zkav.club/infrastructure/zcash/moderation](https://www.zkav.club/infrastructure/zcash/moderation)
* How we publish: [https://www.zkav.club/infrastructure/zcash/publishing](https://www.zkav.club/infrastructure/zcash/publishing)
* Monthly reports: [https://www.zkav.club/infrastructure/zcash/reports](https://www.zkav.club/infrastructure/zcash/reports)

---

## 0) Context and deliverable

This plan covers the workstream to deploy and operate a Zcash-focused PeerTube instance, with clear moderation and sustainability notes.

**Milestone 1 deliverable:** publish this plan publicly (scope, hosting approach, moderation baseline, sustainability notes).

---

## 1) Goals, scope, and non-goals

### Goals (what success looks like)

1. A stable PeerTube “home” for Zcash ecosystem videos that reduces dependence on centralized platforms.
2. A repeatable publishing workflow aligned with PeerTube’s capabilities and a clear internal publication process.
3. Clear moderation + governance baseline that is easy to explain and enforce.
4. Sustainability notes (costs, bandwidth, admin hours, scaling assumptions) tracked monthly.

### Scope (Phase 1 / MVP)

* One PeerTube instance (Zcash branded).
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

---

## 4) Moderation baseline (publish this as policy)

### Roles and access

* Use built-in roles: Administrator, Moderator, User.
* MVP structure:

  * 1–2 admins (infrastructure + policy)
  * 2+ moderators (content + reports)

### Reporting and takedowns

* Accept and process user reports via PeerTube’s reporting tools.
* Response targets (MVP):

  * Illegal/urgent: same day
  * Other reports: 72 hours

### Upload gating

* Enable approval-first / auto-block for new uploads when upload access is broader than admins.

### Federation moderation

* Publish what you will block (hate/harassment instances, spam, etc.).
* Maintain a simple federation log (date + action + reason).

### Documentation outputs

* Public: Moderation policy — [https://www.zkav.club/infrastructure/zcash/moderation](https://www.zkav.club/infrastructure/zcash/moderation)
* Public: How we publish — [https://www.zkav.club/infrastructure/zcash/publishing](https://www.zkav.club/infrastructure/zcash/publishing)
* Public: Monthly reports & sustainability notes — [https://www.zkav.club/infrastructure/zcash/reports](https://www.zkav.club/infrastructure/zcash/reports)
* Internal: moderator runbook (reports, escalations, unfederation)

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
* Transcoding settings (start conservative)
* Federation allow/block approach implemented
* Abuse/report workflow tested end-to-end

### Phase 4 — Pilot publishing workflow

#### Publishing workflow outline (MVP)

* Intake: who requests publication, where requests are tracked, and who owns the upload.
* Upload: uploader posts video to the correct channel, sets visibility to unlisted, and triggers transcoding.
* Metadata minimums (required): title, date/event, speaker/participants (if applicable), description, tags, language, license, and (if used) captions/subtitles.
* Review (if applicable): moderator/admin checks for policy compliance + basic quality (audio intelligibility, correct channel, obvious problems).
* Publish: after approval, set visibility to public, confirm page looks correct, and add to any featured collections/playlists.
* Post-publish: log the link in monthly reporting and note any follow-ups (captioning, edits, takedown requests).

#### Pilot tasks

* Upload 5–10 test videos
* Validate: playback, metadata conventions, captions flow (if used), federation behavior
* Produce the public “How we publish” workflow doc from the outline above

### Phase 5 — MVP launch

Milestone 3 exit criteria: Milestone 3 is complete when all rows in the Phase 5 tracker are marked Done (or Deferred with a brief rationale and a new target date in Notes).

#### MVP tracking (Milestone 3)

Update this block as work progresses. Status values: Not started / In progress / Done / Blocked.

Update cadence: weekly (or after major milestones). If the tracker isn’t updated for more than 7 days, treat statuses as stale.

Targets are best-effort. If a target slips, update the row with a new date and a brief rationale in Notes.

Last tracker update: 2026-02-11

| Area       | Item                                                                 | Owner                              | Target date | Status      | Notes / links                                                                                                  |
| ---------- | -------------------------------------------------------------------- | ---------------------------------- | ----------- | ----------- | -------------------------------------------------------------------------------------------------------------- |
| Docs       | Moderation policy published                                          | Zk Av Club                         | 2026-02-11  | Done        | [https://www.zkav.club/infrastructure/zcash/moderation](https://www.zkav.club/infrastructure/zcash/moderation) |
| Docs       | How we publish published                                             | Zk Av Club                         | 2026-02-11  | Done        | [https://www.zkav.club/infrastructure/zcash/publishing](https://www.zkav.club/infrastructure/zcash/publishing) |
| Docs       | Monthly reports & sustainability notes published                     | Zk Av Club                         | 2026-02-11  | Done        | [https://www.zkav.club/infrastructure/zcash/reports](https://www.zkav.club/infrastructure/zcash/reports)       |
| Planning   | Publish content + usage assumptions                                  | Zk Av Club admins                  | 2026-02-28  | Not started | (Will be added to Section 3)                                                                                   |
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

Monthly reports will be maintained as one rolling page at [https://www.zkav.club/infrastructure/zcash/reports](https://www.zkav.club/infrastructure/zcash/reports).

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

Suggested work plan:

* Feb 1–15: provision + install + basic configuration
* Feb 16–28: harden + pilot workflow + draft workflow docs
* Mar 1–15: seed uploads + federation posture + monitoring/backup verified

---

## 8) Milestone 1 completion record

Milestone 1 is complete when the plan includes the items below. This section is kept as a record for grant tracking.

**Milestone 1 completion date:** 2026-01-28

**Milestone 1 artifact (published):** [https://www.zkav.club/infrastructure/zcash/](https://www.zkav.club/infrastructure/zcash/)

Checklist (Milestone 1):

* Scope statement (what MVP is / isn’t)
* Hosting decision + rationale
* Install method
* Moderation baseline (roles, reports, approval-first, federation posture)
* Sustainability notes + monthly reporting plan
* Timeline to MVP through Mar 31, 2026
