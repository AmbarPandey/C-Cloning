# YouTube Studio Setup — step by step

Do these in order. Steps 1–3 must happen before you create the channel; getting the account type
wrong is the one mistake here that is genuinely painful to undo later.

UI labels shift over time — if a menu name doesn't match, the setting is almost always one level up
or down from where this says.

---

## Step 1 — Google account (do this first)

**Create a dedicated Google account for IPPA.** Do not use your personal account.

Why it matters: the channel becomes a business asset. A separate account means you can grant an
editor access without handing over your personal email, and you can transfer or sell the channel
later without untangling it from your identity.

- [ ] New Google account, e.g. `ippa.studio@gmail.com`
- [ ] **Turn on 2-Step Verification immediately.** A channel with revenue attached is a theft target,
      and channel hijacking is common in this niche.
- [ ] Save recovery codes somewhere offline
- [ ] Add a recovery phone and a recovery email you control

---

## Step 2 — Create a Brand Account channel (not a personal one)

At youtube.com → profile → **Create a channel**, choose the option to create the channel **with a
business or other name**. This creates a *Brand Account*.

| | Personal channel | **Brand Account** |
|---|---|---|
| Tied to one Google identity | Yes | No |
| Multiple managers/owners | No | **Yes** |
| Transferable | Painful | **Yes** |

A Brand Account is what lets you add a freelance editor at Stage B of the
[scaling ladder](../docs/32-future-expansion.md) without sharing your password. Choose it now — 
converting later is possible but fiddly.

- [ ] Channel created as a Brand Account
- [ ] Name set to `IPPA`

---

## Step 3 — Claim the handle

Studio → **Customisation → Basic info → Handle**.

Take the highest available from the [handle candidates](01-CHANNEL-IDENTITY-LOCK.md#handle-candidates).
Claim the matching handle on TikTok, Instagram, and X the same day, even if you don't post there yet —
they cost nothing to hold and are expensive to lose.

- [ ] YouTube handle claimed
- [ ] Same stem reserved on TikTok / Instagram / X

---

## Step 4 — Verify the channel

Studio → **Settings → Channel → Feature eligibility** → verify by phone.

Unlocks custom thumbnails and longer uploads. Takes two minutes and gates things you'll want.

- [ ] Phone verified
- [ ] Custom thumbnails enabled

---

## Step 5 — Branding

Studio → **Customisation → Branding**. Upload the three assets from
[brand art specs](03-brand-art-specs.md).

- [ ] Picture — `IPPA_icon_800.png` (800 × 800)
- [ ] Banner — `IPPA_banner_2560x1440.png` (2560 × 1440)
- [ ] Video watermark — `IPPA_watermark_150.png` (150 × 150), display **entire video**

---

## Step 6 — Basic info

Studio → **Customisation → Basic info**. All text from
[channel metadata](02-channel-metadata.md).

- [ ] Description pasted
- [ ] Business email added (dedicated address, not personal)
- [ ] Country set to your actual country of residence
- [ ] Links left empty for now

---

## Step 7 — Layout

Studio → **Customisation → Layout**.

- [ ] Channel trailer for new visitors → your strongest episode (see
      [trailer guidance](02-channel-metadata.md#channel-trailer))
- [ ] Featured video for returning subscribers → most recent upload
- [ ] Featured sections, in this order:
      1. Shorts
      2. `Best of IPPA`
      3. `PIP & CHIEF`
      4. `Instant Karma`
      5. Playlists

Ordering matters: a new visitor should hit your Shorts shelf and your curated best work before
anything else.

---

## Step 8 — Upload defaults (the biggest time-saver)

Studio → **Settings → Upload defaults**. This is where you buy back minutes on every single upload —
which directly serves the sub-45-minute production target in
[Objectives](../docs/02-objectives.md).

**Basic info tab:**

- [ ] Description → paste the standing block:

```
New twist every day on IPPA. Who deserves the next one? 👇

#shorts #animation #cartoon #comedy #plottwist #karma #funny #instantkarma #satisfying #toon
```

- [ ] Visibility → **Private** (deliberate: forces you through the
      [11-point Publish Gate](../docs/12-stage-2-channel-operating-system.md) before anything goes
      live; you flip to Scheduled by hand)
- [ ] Category → **Comedy**
- [ ] Comments → **Hold potentially inappropriate comments for review**
- [ ] License → Standard YouTube licence
- [ ] Title → leave blank (unique per video)

**Advanced settings tab:**

- [ ] Language → English
- [ ] Caption certification → none
- [ ] Recording date/location → leave blank
- [ ] Altered/synthetic content disclosure → **see step 9**

---

## Step 9 — Two disclosures you must set yourself

These are compliance settings, not creative ones. I'm laying out the factors; **the decisions are
yours to make and you should read YouTube's own guidance before answering.**

### Made for kids

Every channel and video requires this designation. It's a legal classification under children's
privacy law (COPPA in the US and equivalents elsewhere), based on whether content is **directed to
children** — judged by subject matter, characters, and intended audience, not merely by whether it's
"clean."

Relevant facts about IPPA: the target audience defined in
[Stage 1.5](../docs/11-stage-1_5-business-decisions.md) is **16–34**; the content is animated and
family-*safe*; the [Brand Bible](../production/design/BRAND_BIBLE.md) describes a secondary audience
of roughly 8–80.

Note that "made for kids" carries real consequences — it disables personalised ads (lowering RPM),
comments, and several other features. **Read YouTube's official guidance and decide deliberately.
If you're unsure, get professional advice — misdesignating carries regulatory risk.** The existing
[A1 publish package](../production/A1-first-video/08-publish-package.md) correctly leaves this as
"set per your channel policy."

- [ ] Channel-level designation set deliberately, after reading YouTube's guidance

### Altered or synthetic content

YouTube requires disclosure when realistic content is synthetically generated. Clearly-stylised
animation is generally treated differently from realistic synthetic media, but IPPA is
AI-produced end to end, so **read the current policy and disclose per its terms.** Being
scrupulous here directly protects against the **#1 risk in the whole business plan** — monetization
rejection of AI content ([Stage 1.5 risk analysis](../docs/11-stage-1_5-business-decisions.md)).

- [ ] Current policy read
- [ ] Disclosure default set accordingly

---

## Step 10 — Monetization prerequisites

You can't join YPP yet, but do the groundwork now so nothing blocks you at the threshold.

- [ ] Studio → **Earn** → read the current eligibility criteria
- [ ] AdSense account prepared (don't link until eligible)
- [ ] Tax info gathered for your jurisdiction
- [ ] Read the Community Guidelines and the advertiser-friendly content guidelines end to end

Current thresholds (verified Aug 2026 against
[YouTube's official guidance](https://support.google.com/youtube/answer/94522) — re-check before you
apply, these do change):

| Path | Requirement |
|---|---|
| **Full YPP — ad revenue** | 1,000 subscribers **+** either 4,000 valid public watch hours on long-form in 365 days **or** 10 million valid public Shorts views in 90 days |
| **Fan funding tier** | Lower entry at 500 subscribers, unlocking memberships / Super Thanks / Shopping but **not** ad revenue share |

⚠️ **Read [the launch checklist](05-launch-checklist.md#the-ypp-math-problem) before you plan around
these numbers** — the Shorts-only path has a scale problem the current roadmap doesn't account for.

---

## Step 11 — Housekeeping

- [ ] Studio → **Settings → Community → Automated filters** — add blocked words if needed; keep
      "hold potentially inappropriate" on
- [ ] Studio → **Settings → Permissions** — leave as owner-only until you actually hire
- [ ] Bookmark **Analytics → Audience retention**. Per
      [Library 5](../intelligence/05-viewer-psychology-library.md) and the
      [KPI decision trees](../docs/12-stage-2-channel-operating-system.md), the 3-second retention
      number is the metric that drives your weekly decisions. Not subscribers. Not likes.

---

## Verification

Open your channel in a logged-out incognito window on **both** desktop and mobile.

- [ ] Icon is legible at feed size
- [ ] Banner wordmark is fully visible on mobile — nothing important clipped
- [ ] Description reads correctly, hook visible before the "more" cut
- [ ] Handle resolves: `youtube.com/@yourhandle`
- [ ] Playlists visible and correctly ordered
- [ ] Trailer autoplays for a non-subscriber
