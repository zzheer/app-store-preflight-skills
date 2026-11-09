# Checklist: All Apps (Universal Guidelines)

Guidelines that apply to **every** app regardless of category. Check these before every submission.

## Pre-Submission Essentials

- [ ] **2.1** — App is final, complete, tested on-device for crashes and bugs
- [ ] **2.1** — All metadata is complete and accurate (no placeholder text, empty URLs)
- [ ] **2.1** — Demo account provided (or demo mode with prior Apple approval)
- [ ] **2.1** — Backend services are live and accessible during review
- [ ] **2.1(b)** — All configured IAP items are findable and functional (or explained in review notes)
- [ ] **2.1** — Review notes include all 6 required new-submission sections (see `references/rules/metadata/review_notes_new_submission.md`)
- [ ] **2.3.1(a)** — Review notes describe every new feature and product change **with specificity** (generic descriptions are rejected)
- [ ] **2.5.19** — No hidden, dormant, or undocumented features; nothing unlocks after approval (see `references/rules/design/hidden_features.md`)

## App Store Connect Requirements

Not guideline text, but these block submission or distribution:

- [ ] **SDK minimum** — Built with the iOS/iPadOS 26 SDK or later (tvOS, visionOS, watchOS 26 SDK likewise) — required since April 28, 2026
- [ ] **SDK minimum (upcoming)** — Uploads must be built with the iOS/iPadOS 27 SDK or later starting April 2027 ([Apple news](https://developer.apple.com/news/), 2026-09-09)
- [ ] **2.3.6** — Age rating questionnaire answered, including the **social media capability** questions (required since September 2026)
- [ ] **2.3.6** — Age rating questionnaire answers the new **Shared Location** and **Dating & Relationships** questions (available from November 16, 2026; required for all apps by January 12, 2027; dating apps get a minimum 18+ rating) ([Apple news](https://developer.apple.com/news/), 2026-11-02)
- [ ] **Regulated medical device status** — Required if the app is in Health & Fitness / Medical, or declares frequent medical info, and ships in the EEA, UK, or US (see `health_fitness.md`)
- [ ] **iPhone Duo screenshots** — ⚠️ Required for all submissions starting April 2027 (unverified — source needed)
- [ ] **Age assurance laws** — If distributed in Texas, Utah, Louisiana, California, Brazil, Australia, or Singapore: check obligations under the Declared Age Range API and PermissionKit Significant Change API (see `kids.md`)

## Metadata

- [ ] **2.3.7** — App name ≤ 30 characters; unique; no trademark stuffing
- [ ] **2.3.7** — No pricing info, other app names, or irrelevant phrases in metadata
- [ ] **2.3.10** — No other mobile platform or alternative app marketplace names/icons (Android, Google Play, etc.)
- [ ] **2.3.3** — Screenshots show app in use (not just title art, login, or splash)
- [ ] **2.3.4** — App preview videos: screen captures only (no device frames)
- [ ] **2.3.8** — Metadata adheres to 4+ age rating (icons, screenshots, previews)
- [ ] **2.3.9** — Rights secured for all materials; fictional account data in screenshots
- [ ] **2.3.12** — What's New text describes significant changes
- [ ] **2.3.14** — Creative assets (product page header, search result assets): relate to the app or brand, 4+ appropriate, no specific or discounted pricing, no misleading references to other apps, no unverifiable claims
- [ ] **4.1(c)** — No other developer's icon, brand, or product name in your app icon or name without their approval
- [ ] **5.2.5** — No Apple product images in app icon; no confusing Apple trademarks

## Privacy & Data

- [ ] **5.1.1(i)** — Privacy policy linked in App Store Connect AND accessible in-app
- [ ] **5.1.1(i)** — Policy content: what data is collected and how; names third parties it is shared with and confirms they provide equal protection; data retention/deletion policy; how users revoke consent or request deletion ([guidelines](https://developer.apple.com/app-store/review/guidelines/#data-collection-and-storage))
- [ ] **5.1.1(ii)** — User consent secured for all data collection
- [ ] **5.1.1(ii)** — Paid functionality must not be dependent on or require a user to grant access to this data (e.g., a paid tier or ad removal can't require tracking consent)
- [ ] **5.1.1(iii)** — Only request data relevant to core functionality
- [ ] **5.1.1(v)** — If account creation exists, account deletion must be offered
- [ ] **5.1.2(i)** — Explicit permission before sharing personal data with third parties, **including third-party AI** (see `references/rules/privacy/third_party_ai_consent.md`)
- [ ] **5.1.2(i)** — ATT framework required for cross-app tracking
- [ ] **ATT (EU, informational)** — iOS 27.2 adds an alternative ATT prompt in the EU; if your tracking flow targets EU users, verify it against the new prompt ([Apple news](https://developer.apple.com/news/), 2026-09-16)
- [ ] **5.1.2(i)** — Not requiring push notifications, location, or tracking to use the app or receive rewards
- [ ] **Privacy Manifest** — `PrivacyInfo.xcprivacy` includes all Required Reason APIs

## Design & UX

- [ ] **4.1** — Not a copycat of another app
- [ ] **4.2** — Meaningful functionality beyond a repackaged website
- [ ] **4.3(b)** — Not another undifferentiated app in a saturated category (dating, flashlight, wallpaper, simple timer, etc.)
- [ ] **4.8** — If social logins offered, must also offer Sign in with Apple (or equivalent)
- [ ] **4.0** — Sign in with Apple: don't re-ask name/email already provided by SIWA
- [ ] **2.5.1** — Only public APIs; current OS; frameworks for intended purposes
- [ ] **2.5.5** — Fully functional on IPv6-only networks
- [ ] **2.5.14** — Explicit consent for recording user activity
- [ ] **4.5.3** — No spam, phishing, or unsolicited messages via Push Notifications, Live Activities, or Game Center

## Advertising

- [ ] **2.5.18** — Users can report inappropriate or age-inappropriate ads from within the app ([guidelines](https://developer.apple.com/app-store/review/guidelines/#software-requirements))
- [ ] **2.5.18** — Interstitial ads have a visible close/skip control
- [ ] **2.5.18** — No ads in widgets, extensions, App Clips, notifications, keyboards, or watchOS apps

## Business

- [ ] **3.1.1** — Digital content unlocks use IAP
- [ ] **3.2.2(x)** — Not forcing users to rate/review to access features
- [ ] **5.6.1** — Review prompts use the system API (`SKStoreReviewController` / `requestReview`), not a custom prompt
- [ ] **1.5** — Support URL with easy contact method
- [ ] **5.6.2** — Developer identity information is accurate and verifiable
