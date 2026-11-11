# Product launch checklist

Assess each ID once. The criteria below describe evidence to seek, not universal launch requirements. Apply only relevant criteria within an item; record N/A when the whole item is outside scope. A grouped item is Done only when all applicable criteria are supported. Keep source implementation distinct from live verification.

## Brand and presence

- **BR01 — Domain and entry point:** Intended URL resolves; HTTPS and relevant canonical redirects work. For installed tools, verify the intended distribution entry point instead.
- **BR02 — Visual identity:** Product name, logo, favicon, and app/package icons are present where applicable; no placeholder branding.
- **BR03 — Landing or listing page:** Explains the audience, benefit, and main call to action; links to a working entry point.
- **BR04 — Product demonstration:** Accurate screenshots, demo, or examples where users need them to evaluate the product.
- **BR05 — Sharing and contact:** Relevant pages have social preview metadata; a monitored contact method is findable; branded email if applicable.

## Product experience

- **UX01 — Core journey:** A representative user can complete the product's main promised task, with an observable useful result.
- **UX02 — Onboarding:** A new user can start and reach a first useful result; prerequisites and permissions are clear.
- **UX03 — Identity lifecycle:** Signup, login, logout, verification, recovery, and session behavior work as applicable. Respect passwordless, SSO, and account-free designs.
- **UX04 — Interface states:** Applicable empty, loading, success, validation, error, and retry states are useful and accurate.
- **UX05 — Device compatibility:** Key screens and flows work on supported devices, screen sizes, browsers, or operating systems.
- **UX06 — Accessibility:** Key flows support relevant keyboard/focus behavior, semantics, labels, contrast, and assistive technology. Automated results alone do not establish conformance.
- **UX07 — Account controls:** Relevant settings, data export, and account deletion are available as appropriate to the product and its commitments.
- **UX08 — Performance:** Key pages or commands respond acceptably under representative conditions; check obvious loading, layout, and resource issues without inventing a universal threshold.

## Documentation and support

- **DS01 — Quickstart:** Accurate instructions let a new user complete the main task; examples and links work.
- **DS02 — User documentation:** Main workflows, prerequisites, limitations, and likely questions are covered at a depth suitable for this launch.
- **DS03 — Support:** Users can reach a monitored support channel and know what response to expect; do not invent service-level promises.
- **DS04 — Feedback:** A usable path exists for feedback and bug reports.
- **DS05 — Release information:** Current version/release notes and relevant known limitations are discoverable when needed for users to adopt or upgrade.

## Analytics and operations

- **OP01 — Measurement:** Appropriate, minimized events or another deliberate feedback method measure acquisition, first useful action, return usage, and conversion where relevant. Verify delivery when available.
- **OP02 — Error visibility:** Actionable application failures are captured; alerts reach a responsible person. Do not require a particular vendor.
- **OP03 — Availability:** Hosted critical services have appropriate health/uptime checks and alerts; a public status page is conditional on user needs.
- **OP04 — Diagnostic logs:** Relevant logs are accessible for troubleshooting and avoid secrets or unnecessary sensitive data.
- **OP05 — Data recovery:** Stored user data has appropriate backup coverage and retention, with evidence that restoration works. Backup configuration alone does not verify a restore.
- **OP06 — Release recovery:** Deployment/distribution is repeatable, configuration is separated appropriately, and a rollback or recovery path accounts for data migrations where applicable.
- **OP07 — Costs and limits:** Expensive resources have appropriate usage visibility, quotas, budgets, or alerts; avoid surprise unbounded consumption.

## Security, privacy, and trust

- **ST01 — Transport and configuration:** Applicable HTTPS/TLS, cookie/session settings, and browser security controls fit the architecture.
- **ST02 — Authorization:** Protected operations enforce permissions; tenant/user boundaries are checked where applicable. UI hiding alone is insufficient.
- **ST03 — Secrets:** Credentials are kept out of public source, distributable bundles, and logs; server-only credentials stay server-side.
- **ST04 — Abuse protection:** Exposed signup, authentication, uploads, and expensive operations have relevant validation, limits, or other abuse controls.
- **ST05 — Disclosures:** Applicable privacy, terms, and contact information accurately describe the product's actual behavior and operator. Do not require placeholder legal pages.
- **ST06 — Tracking choices:** Collection, retention, and consent/opt-out behavior fit the actual analytics and audience. Check specific legal claims against current authoritative sources when necessary.

## Payments and monetization

Mark this category N/A for a launch without payments; identify external checkout providers or sales-assisted billing before deciding individual applicability.

- **PM01 — Offer:** Pricing, currency, plan limits, trial conditions, and what is included are clear and match enforcement.
- **PM02 — Checkout and fulfillment:** Successful payment grants the correct access exactly as intended; distinguish sandbox evidence from live verification.
- **PM03 — Billing events:** Applicable signed webhooks, retries, duplicate events, failed payments, renewals, and refunds reconcile access and billing correctly.
- **PM04 — Subscription controls:** Applicable upgrade, downgrade, cancellation, and trial-expiry behavior is clear and works.
- **PM05 — Billing records and terms:** Relevant receipts/invoices, tax handling, refund/cancellation terms, and billing contact are configured appropriately. Avoid declaring tax or legal compliance without adequate evidence.

## Discovery and distribution

- **DD01 — Search metadata:** Public pages intended for search have meaningful titles, descriptions, and appropriate canonical URLs.
- **DD02 — Indexing boundaries:** Intended public content is crawlable; staging/private content is protected with authentication where needed. Robots rules are not access control.
- **DD03 — Search tooling:** Sitemap and search-engine verification are configured where useful. These are not universal blockers or guarantees of indexing.
- **DD04 — Functional links and messages:** Key links, downloads, forms, and applicable transactional messages work; source templates alone do not establish delivery.
- **DD05 — First-user distribution:** A concrete audience/channel, launch material, and way to capture interested users exist for the stated launch.
- **DD06 — Representative validation:** Relevant evidence shows intended users can complete the main workflow; distinguish observed behavior from assumptions and developer-only checks.

## Developer platform

Apply only to products exposing developer-facing interfaces. A downloadable developer tool may need packaging and examples without offering an API or SDK.

- **DV01 — API contract:** Applicable endpoint/command documentation covers inputs, outputs, authentication, and errors accurately.
- **DV02 — Credential lifecycle:** Developers can obtain, scope, rotate, and revoke credentials where applicable.
- **DV03 — SDKs:** SDKs for promised/supported languages install and complete a representative task. Additional languages are optional; an SDK is not mandatory for every API.
- **DV04 — Working examples:** Copy-paste examples or a sample app run with documented prerequisites and produce the expected result.
- **DV05 — Compatibility and limits:** Relevant quotas, rate limits, retries, versioning, breaking changes, and deprecation expectations are documented and match behavior.
- **DV06 — Package distribution:** Install/download instructions, package metadata, README, licensing, and intended release artifacts are appropriate and consistent.
- **DV07 — Webhooks:** Where offered, signing verification, retries, duplicate handling, event examples, and local testing instructions are usable.

## Mobile distribution

Mark N/A for products without a native mobile release. A responsive website alone does not require an app-store listing.

- **MB01 — Release build:** Intended build installs and works on supported devices; signing and environment settings suit the release target.
- **MB02 — Store readiness:** Applicable listing assets, support/privacy links, data disclosures, permission explanations, review access, and purchase rules match the app. Verify changing store requirements against official guidance.
- **MB03 — Device lifecycle:** Relevant permission denial, offline/network recovery, background/resume, and upgrade behavior preserve a usable experience and user data.
