## PeerTube for Zcash: Decision + Implementation Plan

**Executive summary (for publication):** Zcash needs its own video infrastructure because the current default requires users to trade privacy for access. Zk Av Club is deploying [watchz.cash](https://watchz.cash), a community-run PeerTube instance for the Zcash ecosystem where viewing and publishing do not depend on surveillance platforms.

This document defines the MVP scope, hosting approach, federation posture, moderation baseline, and sustainability model, and reflects live infrastructure progress.

**Target:** Invite-only alpha by April 30, 2026.

---

**Owner:** Zk Av Club (Lead Organizer)
**Status:** Active (alpha live, April 2026)
Infrastructure execution began March 2026.
**Last updated:** 2026-04-28

---

### Current status (quick view)

The project has moved from deployment into working alpha.

*Last infrastructure action: upload + playback validated; backup + restore completed (April 2026)*

* Public docs: Done
* Architecture decisions: Done (local-first storage)
* Object storage (Wasabi): Backups only
* Server provisioning (Njalla VPS): Complete
* Server hardening: Complete
* Core services (Postgres, Redis, Caddy): Complete
* PeerTube deployment: Complete (working)
* Backups: Complete (rclone + cron + restore tested)
* Monitoring: Not started
* Seed content prep: In progress
* Alpha onboarding: In progress (test uploaders)

**Next milestone:** Operate alpha → upload Zcon and ZecHub videos → validate workflows → refine moderation + scaling

---

### 1) Goals, scope, and non-goals

#### Goals

1. Provide a stable video home for the Zcash ecosystem
2. Offer a privacy-respecting alternative to centralized platforms
3. Establish a repeatable publishing workflow
4. Define moderation and governance
5. Build a sustainable operating model

#### Scope (MVP)

* One PeerTube instance
* Trusted uploader model
* Approval-first publishing
* Backup baseline
* Initial curated content set

#### Non-goals

* Fully open publishing
* Large-scale migration
* Multi-node infrastructure

---

### 2) Key decisions (MVP)

#### Hosting

* Njalla VPS (max tier)
* Debian 12
* ZFS

#### Storage (April 2026 update)

* **Primary:** Local storage (Njalla)
* **Backup:** Wasabi (rclone)

Object storage was tested for delivery and abandoned. System is now **local-first** due to complexity and poor fit for ingest-heavy workflows.

#### Deployment

* Docker Compose

#### Federation

* Curated allow/block model

#### Access model

* Public registration (interaction only)
* Trusted uploaders
* Approval-first workflow

---

### 3) Requirements and assumptions

Usage assumptions will be validated through alpha usage rather than pre-estimated.

---

### 4) Moderation policy (summary)

* Admin and moderator roles
* Approval-first publishing
* Curated federation posture

Workflows are being tested during alpha.

---

### 5) Deployment plan (execution overview)

#### Phase 1 — Infrastructure (completed)

* Server provisioned and secured

---

#### Phase 2 — Core services (completed)

* ZFS, PostgreSQL, Redis, Caddy configured

---

#### Phase 3 — PeerTube deployment (completed)

* PeerTube running at watchz.cash
* Connected to DB + cache

Note: SMTP not yet configured

---

#### Phase 4 — Storage integration (revised)

* Wasabi → backups only
* Local storage → playback

---

#### Phase 5 — Validation (completed)

* Upload → transcode → playback working
* Resumable uploads configured
* 480p / 720p / 1080p outputs verified

---

#### Phase 6 — Invite-only alpha (active)

* Backups active (rclone + cron)
* Restore tested
* Public accounts (interaction only)
* Upload restricted
* Test uploaders onboarded
* P2P/WebTorrent disabled

---

### 6) MVP milestone (April 30, 2026)

watchz.cash is in **invite-only alpha** with:

**Technical**

* Domain + HTTPS
* PeerTube operational
* DB + cache running
* Backups active

**Product**

* Restricted uploads
* Public interaction enabled
* Moderation baseline (in testing)

**Content**

* Channels created
* Initial uploads in progress

---

### 7) Timeline

#### March

* Infrastructure setup

#### April

* Deployment completed
* Storage model revised
* Validation completed
* Alpha launched

---

### 8) Sustainability notes

#### Cost drivers

* Storage
* Bandwidth
* Transcoding

#### Approach

* Constrained scope
* Measure real usage
* Scale based on demand

---

### 9) Notes and updates

April marks the transition to a working alpha system.

**Key changes:**

* Storage: object → local-first
* Backups implemented
* Pipeline validated
* Alpha usage began

**Next focus:**

* Upload Zcon + ZecHub content
* Observe performance and costs
* Refine moderation and workflows
* Plan scaling strategy

For questions or collaboration: [contact Zk Av Club](https://zkav.club/#join-the-club).
