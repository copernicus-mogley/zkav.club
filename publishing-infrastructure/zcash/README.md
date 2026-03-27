## PeerTube for Zcash: Decision + Implementation Plan

**Executive summary (for publication):** Zcash needs its own video infrastructure because the current default requires users to trade privacy for access.

Zk Av Club is actively deploying `watchz.cash`, a community-run PeerTube instance for the Zcash ecosystem where viewing and publishing do not depend on surveillance platforms.

This document defines the MVP scope, hosting approach, federation posture, moderation baseline, and sustainability model, and reflects live infrastructure progress and an active build timeline.

**Target:** Invite-only alpha by April 30, 2026.

---

**Owner:** Zk Av Club (Lead Organizer)

**Status:** Active (deployment in progress)

Infrastructure execution began March 2026.

**Last updated:** 2026-03-27

---

### Current status (quick view)

The project is in an active deployment phase, with infrastructure already underway.

*Last infrastructure action: server provisioned and hardened (March 2026)*

* Public docs: Done
* Architecture decisions: Done
* Object storage (Wasabi): Complete
* Server provisioning (Njalla VPS): Complete
* Server hardening: Complete
* Core services: In progress
* PeerTube deployment: Not started
* Backups + monitoring: Not started
* Seed content prep: In progress

**Next milestone:** Core services → PeerTube install → working instance

---

### 0) Context and deliverable

This page is the canonical public tracker for deploying and operating a Zcash-focused PeerTube instance.

This instance is intended for Zcash ecosystem contributors, educators, and community publishers.

Instance URL: `watchz.cash` (in progress)

Current focus is MVP execution.

---

### 1) Goals, scope, and non-goals

#### Goals

1. Provide a stable video home for the Zcash ecosystem
2. Offer a privacy-respecting alternative to centralized platforms
3. Establish a repeatable publishing workflow
4. Define clear moderation and governance
5. Build a sustainable operating model

#### Scope (MVP)

* One PeerTube instance (`watchz.cash`)
* Trusted uploader model
* Approval-first publishing
* Backup and monitoring baseline
* Initial curated content set

#### Non-goals

* Public open registration
* Large-scale content migration
* Complex multi-node infrastructure

---

### 2) Key decisions (MVP)

#### Hosting

* Provider: Njalla
* VPS tier: highest available (accepted constraint)
* OS: Debian 12
* Filesystem: ZFS

#### Storage

* Object storage: Wasabi (S3-compatible)
* Local: application + database + cache
* Remote: video assets

Wasabi setup is complete and ready for integration.

#### Deployment

* Method: Docker Compose

#### Federation

* Curated allow/block model

#### Access model

* Invite-only accounts
* Trusted uploaders
* Approval-first workflow

---

### 3) Requirements and assumptions

Usage assumptions will be validated through real usage during alpha rather than projected in advance, allowing infrastructure and cost decisions to be based on observed behavior rather than estimates.

---

### 4) Moderation policy (summary)

MVP baseline:

* Admin and moderator roles
* Approval-first publishing
* Curated federation posture

For details read the full [moderation policy](https://zkav.club/publishing-infrastructure/zcash/moderation)

---

### 5) Deployment plan (execution overview)

The following phases outline the execution path at a high level; detailed internal runbooks are maintained separately.

#### Phase 1 — Infrastructure (completed)

* Server provisioned and secured
* Base system hardened and accessible

---

#### Phase 2 — Core services (in progress)

**Goal:** Establish a stable system foundation

* Configure storage (ZFS)
* Set up database and cache services
* Configure reverse proxy and network access

**Exit criteria:**

* Storage is mounted and operational
* Core services are running and reachable
* Server responds over HTTP/HTTPS

---

#### Phase 3 — PeerTube deployment

**Goal:** Bring the application online

* Deploy PeerTube
* Connect to database and cache
* Configure domain and HTTPS
* Enable email (SMTP)

**Exit criteria:**

* `watchz.cash` is reachable over HTTPS
* Admin access works
* Email functionality is verified

---

#### Phase 4 — Storage integration

**Goal:** Move media handling to object storage

* Connect PeerTube to Wasabi
* Validate upload → storage → playback flow
* Minimize reliance on local storage

**Exit criteria:**

* Media is stored remotely
* Playback works reliably
* End-to-end flow is validated

---

#### Phase 5 — Validation

**Goal:** Confirm system reliability

* Upload and process test videos
* Validate playback across environments
* Test moderation and admin workflows

**Exit criteria:**

* Core workflows function without errors
* System is usable without manual intervention

---

#### Phase 6 — Invite-only alpha preparation

**Goal:** Prepare for controlled usage

* Configure backups and monitoring
* Finalize baseline policies
* Prepare initial content set

---

### 6) MVP milestone (April 30, 2026)

By April 30, `watchz.cash` will be in invite-only alpha with:

#### Technical foundation

* Working domain and HTTPS
* PeerTube deployed
* Database and cache operational
* Backups and monitoring active

#### Product foundation

* Restricted registration
* Upload limits defined
* Moderation workflow in place
* Basic policy pages published

#### Content foundation

* 3 Zcash channels
* 10–20 initial videos
* Basic taxonomy and structure

---

### 7) Timeline

#### March

* Infrastructure setup (completed)
* Core services in progress

#### April

* Complete deployment
* Validate system
* Prepare content and policy baseline

#### April 30

* Invite-only alpha milestone

---

### 8) Sustainability notes

#### Cost drivers

* Storage
* Bandwidth
* Transcoding compute

#### Approach

* Start with constrained scope
* Measure real usage
* Scale based on observed demand

---

### 9) Notes and updates

This page is a living document and will be updated as the project progresses.

Key updates will include:

* Changes to deployment status and milestones
  * [Monthly Reports and Sustainability Notes](/publishing-infrastructure/zcash/reports)
* Infrastructure or architecture adjustments (reflected in this page)
* Updates to moderation, publishing, or access policies:
  * [Moderation Policy](https://zkav.club/publishing-infrastructure/zcash/moderation)
  * [Publishing](https://zkav.club/publishing-infrastructure/zcash/publishing)
* Observations from alpha usage (performance, costs, workflows)

For questions, feedback, or collaboration inquiries, [contact us](/#join-the-club).

Future updates will be reflected in the “Last updated” field at the top of this page.
