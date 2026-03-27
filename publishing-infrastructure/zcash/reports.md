## Monthly Reports and Sustainability Notes

### Purpose

This page is the rolling operational record for the Zcash PeerTube instance: what changed, what was shipped, what broke (if anything), what it cost, and what comes next.

**Status:** Applies to MVP (invite-only alpha, April 2026)

**Last updated:** 2026-03-27

Related pages:

* [How we publish](/publishing-infrastructure/zcash/publishing)
* [Moderation policy](/publishing-infrastructure/zcash/moderation)
* [Project hub](/publishing-infrastructure/zcash/)

---

### How this page works

* This is one rolling page (not one page per month)
* Each month has its own section (for example: `## 2026-03`)
* Update the current month as work happens
* At month end, add a short summary and start the next month
* Update at least once per month (weekly updates recommended during active build)

---

### What gets reported

If it moved the project forward, it belongs here:

* Infrastructure progress (provisioning, deployment, configuration)
* Workflow and policy changes
* Testing and validation
* Issues, blockers, and decisions

The source of truth for current system state is the [Project hub](/publishing-infrastructure/zcash/). This page records what changed and why.

---

### Pre-launch reporting

Before the instance is live, reports track project progress rather than runtime operations.

* Metrics that do not exist yet are marked: N/A (pre-launch)
* Focus is on decisions, setup progress, and readiness

---

### Reporting units

* Costs are reported in USD

---

## 2026-01

### Project status (pre-launch)

* Current system state: /publishing-infrastructure/zcash/
* Summary: Published the project hub (Milestone 1)

### Highlights

* Published PeerTube for Zcash Decision + Implementation Plan
* Defined MVP model: invite-only, trusted uploaders, approval-first publishing

### Milestone progress

* Decisions made:
  * Confirmed PeerTube as deployment target
  * Defined moderation baseline and curated federation
  * Defined initial channel ownership model
* Infrastructure: Not started
* Workflow/policy: Plan published
* Testing: N/A (pre-launch)
* Blockers:
  * Content and usage assumptions not yet defined

### Operations

* Uploads: N/A (pre-launch)
* Uptime/incidents: N/A (pre-launch)
* Backups: N/A (pre-launch)
* Updates: N/A (pre-launch)

### Moderation

* Reports: N/A (pre-launch)
* Actions: N/A (pre-launch)
* Federation changes: N/A (pre-launch)

### Costs

* Hosting: $0
* Storage: $0
* Bandwidth: $0
* Other: $0

### Admin time

* ~8 hours (research, design, documentation)

### Storage

* N/A (pre-launch)

### Risks

* Delayed assumptions may delay provisioning

### Next focus

* Publish usage assumptions
* Begin provisioning
* Prepare pilot uploads

---

## 2026-02

### Project status (pre-launch)

* Current system state: /publishing-infrastructure/zcash/
* Summary: Built operational documentation and tracker

### Highlights

* Published moderation policy, publishing workflow, and reports page
* Refactored hub into operational tracker
* Clarified privacy posture and embed policy

### Milestone progress

* Decisions made:
  * Approval-first publishing
  * Rolling reports model
  * No third-party embeds on instance pages
* Infrastructure: Not started
* Workflow/policy: Completed and published
* Testing: N/A (pre-launch)
* Blockers:
  * Usage assumptions pending

### Operations

* Uploads: N/A (pre-launch)
* Uptime/incidents: N/A (pre-launch)
* Backups: N/A (pre-launch)
* Updates: N/A (pre-launch)

### Moderation

* Reports: N/A (pre-launch)
* Actions: N/A (pre-launch)
* Federation changes: N/A (pre-launch)

### Costs

* Hosting: $0
* Storage: $0
* Bandwidth: $0
* Other: $0

### Admin time

* ~8 hours (documentation, coordination, structure)

### Storage

* N/A (pre-launch)

### Risks

* Delay in assumptions may delay provisioning

### Next focus

* Publish usage assumptions
* Begin provisioning and install
* Start pilot uploads once live

---

## 2026-03

### Project status (pre-launch)

* Current system state: /publishing-infrastructure/zcash/
* Summary: Began infrastructure build for `watchz.cash` and moved the project from planning into active deployment.

### Highlights

* Provisioned VPS (Njalla) and completed initial server hardening
* Set up object storage (Wasabi) for media
* Aligned hub, moderation, and publishing pages into a consistent system
* Defined and began executing the deployment plan toward invite-only alpha

### Milestone progress

* Decisions made:
  * Storage architecture: local app + DB/cache, media on S3-compatible storage (Wasabi)
  * Deployment path: Docker Compose on single VPS (MVP)
* Infrastructure:
  * VPS provisioned and secured (firewall, SSH hardening)
  * Wasabi bucket configured and ready
  * Core services setup started (ZFS, Postgres, Redis, reverse proxy in progress)
* Workflow/policy:
  * Publishing workflow finalized for MVP (invite-only, trusted uploaders, approval-first)
  * Moderation policy aligned with hub and publishing pages
* Testing:
  * No end-to-end tests yet (awaiting PeerTube install)
* Blockers:
  * None blocking; remaining work is execution (core services → PeerTube install)

### Operations

* Uploads: N/A (pre-launch)
* Uptime/incidents: N/A (pre-launch)
* Backups: Not yet configured
* Updates: Base system updates applied during server setup

### Moderation

* Reports: N/A (pre-launch)
* Actions: N/A (pre-launch)
* Federation changes: N/A (pre-launch)

### Costs

* Hosting: VPS active (monthly cost incurred)
* Storage: Wasabi active (minimal usage)
* Bandwidth: negligible (pre-launch)
* Other: $0

### Admin time

* ~12–16 hours (provisioning, storage setup, system alignment, documentation)
* Main time sinks: server setup and hardening, storage configuration, cross-page documentation alignment

### Storage

* N/A (pre-launch; no media uploaded yet)

### Risks

* Configuration errors during initial service setup (DB, proxy, storage integration)
* First end-to-end upload/transcode may reveal performance or config issues

### Next focus

* Complete core services (ZFS, Postgres, Redis, proxy)
* Install and configure PeerTube
* Connect Wasabi and validate upload → storage → playback flow
* Run first test uploads and validate workflow

---

## Notes

This page is a living document and will be updated as the project progresses.

Updates reflect changes in infrastructure, workflow, moderation, and costs.

For current system state, see:

* [Project hub](/publishing-infrastructure/zcash/)
* [How we publish](/publishing-infrastructure/zcash/publishing)
* [Moderation policy](/publishing-infrastructure/zcash/moderation)
