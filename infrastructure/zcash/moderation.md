# PeerTube for Zcash — Companion Docs (v0.1)

This document contains v0.1 drafts of the three companion documents referenced by the PeerTube for Zcash plan:

1. Moderation Policy (Public)
2. How We Publish (Public)
3. Sustainability Notes (v1 template)

---

## 1) Moderation Policy (Public) — v0.1

### Purpose

This PeerTube instance exists to publish and steward Zcash ecosystem video in a way that supports long-term community access and responsible operations.

### Who this policy applies to

* Anyone viewing content on the instance
* Anyone with an account on the instance
* Any channel owner, uploader, moderator, or administrator

### Roles

* **Administrators:** instance configuration, security, federation policy, account creation controls, backups/updates, and final escalation authority.
* **Moderators:** handle reports, enforce this policy, and maintain federation decisions log.
* **Channel owners:** responsible for content and metadata quality within their channels; coordinate uploads with trusted uploaders.
* **Trusted uploaders:** may upload to specific channels as authorized; uploads are unlisted until approved.

### Account access (MVP)

* Registration is **invite-only**.
* Uploading is limited to a **trusted uploader list**.

### Publishing workflow and visibility (MVP)

* New uploads are **unlisted until approved**.
* A video is “published” when it is **public** and meets the metadata minimums.

### What is allowed

We aim to host content that is relevant to the Zcash ecosystem, including (non-exhaustive):

* Conference/event recordings
* Tutorials and technical talks
* Interviews and community updates
* Educational content that supports Zcash adoption and understanding

### What is not allowed

The instance will not host content that includes:

* Illegal content or instructions facilitating illegal activity
* Harassment, hate, or targeted abuse
* Non-consensual intimate imagery
* Doxxing or sharing private personal information
* Malware, phishing, or scams
* Spam or misleading impersonation

### Reporting

* Viewers can report videos/accounts via PeerTube’s reporting tools.
* Include as much detail as possible (timestamps, description of issue).

### Response targets (MVP)

* **Illegal/urgent:** same day
* **Other reports:** within 72 hours

### Enforcement actions

Depending on severity and context, actions may include:

* Requesting edits/clarifications from the uploader/channel owner
* Unlisting or removing a video
* Suspending or removing uploader access
* Suspending an account
* Instance-level federation actions (block/unfollow)

### Appeals

* Users may appeal moderation decisions by contacting the admins via the instance contact email.
* Appeals should include the link, a description, and the requested remedy.

### Federation policy (MVP)

* Federation is **curated**.
* We may block or unfollow instances that routinely distribute spam, harassment/hate, or other policy-violating content.
* We maintain a simple federation log (date + action + reason).

### Transparency

We will publish:

* This moderation policy
* A high-level description of our federation posture
* Sustainability notes (cost drivers and how operations are supported)

---

## 2) How We Publish (Public) — v0.1

### What this is

This page explains how videos are prepared, uploaded, reviewed, and published on the Zcash PeerTube instance.

### Who publishes here (MVP)

* Accounts are invite-only.
* Uploads are limited to a trusted uploader list.
* Channel owners coordinate what gets published in their channels.

### Channels and ownership (MVP)

* **Zcash Foundation — Zcon (historic + new):** channel owner is Zcash Foundation.

  * During MVP, Zk Av Club admins upload and manage metadata for historic Zcon videos in coordination with Zcash Foundation.
* **ZecHub:** channel owner is ZecHub.

  * During MVP, this channel holds ZecHub programming (and other approved ecosystem content unless/until additional channels are created late MVP).

### Intake

A video enters the pipeline via one of:

* A channel owner request (planned batch, event drop, etc.)
* An uploader request (if they are on the trusted uploader list)

Intake requests should specify:

* Which channel
* Title + date/event
* Any known rights/consent constraints (if applicable)

### Upload

The uploader:

* Uploads to the correct channel
* Sets visibility to **unlisted**
* Triggers transcoding (default settings)
* Adds required metadata (see below)

### Metadata minimums (required)

* Title
* Date/event
* Speaker/participants (if applicable)
* Description (what it is, context, links)
* Tags
* Language
* License
* Captions/subtitles (if available; otherwise mark as “not available yet”)

### Review (MVP)

A moderator/admin checks:

* Policy compliance
* Correct channel placement
* Basic quality (audio intelligibility; obvious technical issues)
* Metadata minimums

### Publish

After approval:

* Set visibility to **public**
* Add to any relevant playlists/collections
* Confirm playback on web + mobile

### Post-publish

* Log link in monthly reporting
* Note follow-ups (captions, edits, corrections, takedown requests)

### Changes and corrections

If a published video needs updates:

* Minor metadata fixes may be applied immediately
* Substantive edits (content removals, sensitive material) should be coordinated with the channel owner and admins

---

## 3) Sustainability Notes (v1 template) — v0.1

### Purpose

This section documents the operational reality of running the instance: what costs money, what takes time, what changed this month, and what we’re doing about it.

### Cost drivers

* Storage growth
* Outbound bandwidth spikes
* Transcoding compute

### Scale triggers (MVP starting thresholds)

We revisit these after 30–60 days of real usage:

* Disk usage > 70% (sustained for 7 days)
* Bandwidth costs > $200/month (for 2 consecutive months)
* Moderation queue > 10 reports/week (for 2 consecutive weeks)
* Admin time > 10 hours/week (sustained for 4 weeks)

### What we report monthly (grant-aligned)

* Upload count + links
* Hosting/bandwidth costs
* Admin hours

Recommended additions:

* Storage growth (GB/month)
* Moderation load (reports/week)

### Monthly update template

**Month:** YYYY-MM

## **Highlights**

## **New uploads (count + links)**

**Ops notes**

* Availability/uptime incidents:
* Backups status (last successful restore test date):
* Updates applied (PeerTube version, OS updates):

**Moderation notes**

* Reports received:
* Actions taken:
* Federation changes (date + action + reason):

**Costs**

* Hosting:
* Storage:
* Bandwidth:
* Other:

**Admin time**

* Hours (estimate):
* Main time sinks:

## **Risks / watch items**

## **Next month focus**
