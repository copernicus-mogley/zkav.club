# How We Publish (Public) — v0.1

## What this is

This page explains how videos are prepared, uploaded, reviewed, and published on the Zcash PeerTube instance.

Project hub: [https://www.zkav.club/infrastructure/zcash/](https://www.zkav.club/infrastructure/zcash/)

Moderation policy: [https://www.zkav.club/infrastructure/zcash/moderation](https://www.zkav.club/infrastructure/zcash/moderation)

Monthly reports: [https://www.zkav.club/infrastructure/zcash/reports](https://www.zkav.club/infrastructure/zcash/reports)

## Who publishes here (MVP)

* Accounts are invite-only.
* Uploads are limited to a trusted uploader list (people the channel owner and admins have approved to upload).
* Channel owners coordinate what gets published in their channels.

## Channels and ownership (MVP)

* **Zcash Foundation — Zcon (historic + new):** channel owner is [Zcash Foundation](https://zfnd.org/).

  * During MVP, Zk Av Club admins upload and manage metadata for historic Zcon videos in coordination with Zcash Foundation.

* **ZecHub:** channel owner is [ZecHub](https://zechub.wiki/).

  * This channel holds ZecHub programming during MVP (and other approved ecosystem content unless/until additional channels are created late MVP).
  * “Other approved ecosystem content” is approved to publish by the ZecHub channel owner; admins can block/unlist content for policy or safety reasons.

## Request to publish (how videos get in line)

“Request to publish” just means: someone tells us *which video should be posted, where it should live, and what it’s called*.

A publish request can come from:

* The channel owner (e.g., “Please publish this batch of Zcon videos”)
* A trusted uploader (someone the channel owner and admins have approved to upload to that channel)

A publish request should include (plain-language minimums):

* Which channel it should go on (Zcash Foundation—Zcon, or ZecHub)
* What the video should be titled
* The date and event (if there is one)
* Anything sensitive we should know up front (for example: someone asked not to be shown, a section should be cut, or consent is unclear)

If you’re wondering why this exists at all: it prevents videos from being uploaded “randomly” without context, and it helps channel owners stay in control of what appears on their channel.

Right now, publish requests are coordinated directly between the channel owner and Zk Av Club admins (a shared request form/link may be added later).

## Upload

The uploader:

* Uploads the video to the correct channel
* Sets it to **unlisted** (so it’s not public yet)
* Lets PeerTube create the viewing versions (transcoding)
* Fills in the required info (see below)

## Metadata minimums (required)

Fill these in for every video (with quick examples):

* **Title** — clear, specific title

  * Zcon talk example: “Zcon: Shielded Wallet UX — Talk by ___”
  * Update example: “Zcash Ecosystem Update — Week of 2026-02-xx”

* **Date/event** — date + event name (if any)

  * Zcon talk example: “2025-xx-xx — Zcon”
  * Update example: “2026-02-xx — ZecHub”

* **Speaker/participants** — names/handles if applicable

  * Zcon talk example: “Speaker: ___”
  * Update example: “Hosts: ___”

* **Description** — 2–5 sentences + key links

  * Zcon talk example: “Overview + agenda + slides link”
  * Update example: “What changed this week + links”

* **Tags** — 3–8 useful tags

  * Zcon talk example: “zcon, talk, wallets, usability”
  * Update example: “update, ecosystem, dev, community”

* **Language** — primary language (example: “en”)

* **License** — how it may be reused

  * Example: “CC BY 4.0” (if that’s what the channel owner chooses)

* **Captions/subtitles** — attach if available; otherwise note status

  * Example: “Captions: coming soon” or “Captions: not available yet”

License note (MVP): the channel owner decides the license. If the license is unclear, keep the video unlisted until the channel owner confirms.

## Naming conventions (recommended)

Use consistent titles so videos are easy to find:

* Talks: `Event: Talk title — Speaker`
* Updates: `Zcash Ecosystem Update — Week of YYYY-MM-DD`

## Review (MVP)

Before anything goes public, a moderator/admin does a quick check:

* Is it allowed under the moderation policy?
* Is it on the right channel?
* Is the audio/video basically usable?
* Does it have the required info filled in (title, date/event, description, etc.)?

Approval checklist (quick):

* Visibility is **unlisted** until approved
* Title is clear + matches the content
* Date/event is filled in
* Description has context + at least one helpful link (if available)
* Tags + language + license are set
* Captions status is noted (attached or “coming soon / not available yet”)
* No third‑party video embeds (YouTube/Vimeo) are added to the description (link out instead)

## Publish

After approval:

* Set visibility to **public**
* Add to any relevant playlists/collections
* Confirm playback on web + mobile

## Privacy + embeds

* We avoid embedding third‑party video players (YouTube/Vimeo) on instance pages by default. Link out instead.
* PeerTube-hosted videos may be embedded on other websites, forums, or chats.

## After publishing

* We add the link to the rolling monthly report
* We note any follow-ups (captions, small fixes, corrections, takedown requests)

## Changes and corrections

If a published video needs updates, here’s how we handle it:

1. **Small fixes (metadata-only)**

   * Examples: title tweaks, tag fixes, description links, playlist placement
   * Usually done immediately

2. **Visibility changes (unlist / relist)**

   * Used when something needs review, corrections, or time-sensitive handling
   * Coordinate with the channel owner; moderators/admins may unlist for policy or safety reasons

3. **Major changes (replace or remove)**

   * Used for substantive edits (content removals, sensitive material, rights/consent issues)
   * Requires coordination between the channel owner and admins
   * When possible, we note what changed and why (without exposing personal information)

## Change log

* 2026-02-11: Published/updated v0.1 with plain-language workflow, approval checklist, metadata examples, and privacy/embeds guidance.
