# Rule: Pricing Claims and "Free" Wording in a Paid App
- **Guideline**: 2.3.1(a), 2.3.7, Section 3 (Business) – Accurate Metadata / Pricing
- **Severity**: REJECTION
- **Category**: metadata

## What to Check
Metadata must not misstate what the app costs ([guidelines](https://developer.apple.com/app-store/review/guidelines/)):

- **2.3.1(a)** — No false prices or misleading descriptions of what the user pays.
- **2.3.7** — No pricing information in app name, subtitle, keywords, or screenshots. This applies to every app, free or paid.
- **"Free" claims** — A paid-upfront app must not call itself "free", "gratis", "kostenlos", "gratuit", "ücretsiz", etc. in any locale.
- **Section 3 intro** — Pricing is up to you, but Apple rejects apps that try to cheat users with irrationally high prices and "clear rip-offs". *Practitioner guidance, not guideline text:* a paid-upfront app that also charges IAP or shows ads invites that scrutiny, so the metadata and review notes should make clear what the upfront price includes and what costs extra or shows ads.

## How to Detect

### Check the price tier
Open App Store Connect → your app → Pricing and Availability and note whether the base price is above free. The 2.3.7 pricing-word check below applies to all apps; the "free" claim check applies only to paid apps.

### Grep metadata for price words (all apps) and "free" words (paid apps)
```bash
grep -rniE "\bfree\b|gratis|kostenlos|gratuit|gratuito|ücretsiz|免费|無料|무료|\\\$[0-9]|€[0-9]|[0-9]+ ?(usd|eur|try)|price|discount|% off" ./metadata
```
Treat hits as candidates to review, not automatic rejections. ❌ when a price appears in the name, subtitle or keywords of any app, or when a paid app calls itself free anywhere. Phrases like "ad-free", "free updates" or "discount calculator" are usually fine in the description.

### Paid + IAP/ads combination
1. Confirm whether the binary includes an ads SDK (AdMob, AppLovin, etc.) or StoreKit IAP products.
2. If yes and the app is paid upfront, check that the description states which features need IAP and whether ads are shown.

## Resolution
1. Remove "free" and price wording from metadata of paid apps in every locale.
2. Remove prices from name, subtitle, keywords, and screenshots; let the App Store show the price.
3. For paid apps with IAP or ads: state clearly in the description what the upfront price includes, what is sold via IAP, and whether ads appear; consider removing ads from the paid tier.
4. Ensure any stated price or discount matches App Store Connect in every storefront.

## Example Rejection
> **Guideline 2.3.1 - Performance - Accurate Metadata**
>
> The app's metadata includes inaccurate pricing information. Specifically, the app description states the app is free, but the app is offered at a price on the App Store.
>
> Next Steps
>
> Revise the app's metadata to remove inaccurate pricing references.
