# Rule: Pricing Claims and "Free" Wording in a Paid App
- **Guideline**: 2.3.1(a), 2.3.7, Section 3 (Business) – Accurate Metadata / Pricing
- **Severity**: REJECTION
- **Category**: metadata

## What to Check
Metadata must not misstate what the app costs ([guidelines](https://developer.apple.com/app-store/review/guidelines/)):

- **2.3.1(a)** — No false prices or misleading descriptions of what the user pays.
- **2.3.7** — No pricing information in app name, subtitle, keywords, or screenshots.
- **"Free" claims** — A paid-upfront app must not call itself "free", "gratis", "kostenlos", "gratuit", "ücretsiz", etc. in any locale.
- **Section 3 intro** — Pricing is up to you, but Apple rejects apps that try to cheat users with irrationally high prices and "clear rip-offs". A **paid-upfront app that also charges IAP or shows ads** is high-risk: the metadata and review notes must make clear what the upfront price includes and what costs extra or shows ads.

## How to Detect

### Check the price tier
Open App Store Connect → your app → Pricing and Availability and note whether the base price is above free. If the app is free, only the IAP/ads wording and false-price checks apply.

### Grep metadata for price and "free" words (paid apps)
```bash
grep -rniE "\bfree\b|gratis|kostenlos|gratuit|gratuito|ücretsiz|免费|無料|무료|\\\$[0-9]|€[0-9]|[0-9]+ ?(usd|eur|try)|price|discount|% off" ./metadata
```
Any hit in name, subtitle, keywords, description, promotional text, or What's New for a paid app → ❌ (review each hit; "free updates" or "ad-free" may be acceptable in the description but never in name/subtitle/keywords).

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
