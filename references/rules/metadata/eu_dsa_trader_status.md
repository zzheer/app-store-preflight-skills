# Rule: EU Digital Services Act Trader Status
- **Guideline**: Not an App Review guideline: EU Digital Services Act (DSA) compliance information in App Store Connect
- **Severity**: REJECTION (blocks submission until the status is declared; apps without a verified trader status are not offered on EU storefronts)
- **Category**: metadata

## What to Check
Every developer must declare in App Store Connect whether they are a **trader** under EU law, even if they do not distribute apps in the EU. Apple cannot decide this for you ([Apple: Manage EU DSA trader requirements](https://developer.apple.com/help/app-store-connect/manage-compliance-information/manage-european-union-digital-services-act-trader-requirements/), fetched 2026-11-09).

The status is needed before submitting **new apps and updates**. Apple announced that, from 17 February 2025, apps without trader status information are removed from the App Store in the EU until the information is provided ([Apple Developer news, 2025](https://developer.apple.com/news/); verify the current wording before relying on the date).

You are likely a trader if the app is part of your trade, business, craft or profession. Apple's factors include revenue from the app (paid app, In-App Purchases, ads), commercial promotion, VAT registration and professional development of the app.

Traders must provide:
- **Organizations**: the D-U-N-S address (shown automatically) plus a phone number and an email address.
- **Individuals**: an address or P.O. box, a phone number and an email address.
- **All traders**: payment account details (if not entered yet) and a certification that they offer only products or services that comply with EU law.
- **Verification**: email and phone are verified with two-factor authentication; documents proving the business name and address are required.
- **Optional**: a Labels and Markings URL for EU-required labels.

If you declare that you are **not** a trader, EU customers are told that consumer-protection rights do not apply to their contracts with you.

## How to Detect
This is account and app metadata, not code:

1. In App Store Connect, open **Business** and check the account's **Digital Services Act** status, then open the reviewed app's **App Information** and check the status shown for that app (App Store Connect can show it per app; the app's effective declaration is what counts).
2. Flag the check if the effective status is missing, or if the app earns money (paid, IAP, subscriptions or ads) while it is declared **not a trader**.
3. Check that the published phone number and email are monitored: they appear on the EU product page.

## Resolution
1. Decide the trader status (a monetized app usually means trader) for the account and, where shown, for the reviewed app.
2. Enter and verify the contact details and documents in App Store Connect.
3. Add a Labels and Markings URL if the app or its products need EU labels.
4. Record the decision in the release checklist and re-check it when the app's monetization changes.

## Example Rejection
> Before you can submit this app, confirm your trader status under the EU Digital Services Act in App Store Connect.
