# JBD NY Drop 1 — Wholesale Allocation Signup

Single-page click-through signup site for NY dispensaries to reserve their tier in the JBD NY 2026 Drop 1 wholesale release.

## Flow

1. **Pick tier** — Tier 1 ($9,000) / Tier 2 ($4,500) / Tier 3 ($2,250)
2. **Store info** — name, signer, license, contact
3. **Review & agree** — full allocation agreement + 3 acknowledgement checkboxes
4. **Sign** — HTML5 canvas signature pad (works on touch + mouse)
5. **Confirmation** — POST to `app.cannacrypted.com/api/event/signup`, downloadable signed PDF

## Tier content

Tier definitions live in `index.html` under `const TIERS = [...]`. Edit the `features`, `price`, and `deposit` fields directly — UI re-renders from that array.

## Agreement copy

Lives in `const AGREEMENT_TEMPLATE` in `index.html`. **This is placeholder copy — get legal review before going live.**

## Backend

Posts to `/api/event/signup` on the jbd-glass Flask app. Backend persists the signup row + signature image, emails confirmation via Resend, and exposes admin list at `/api/admin/event/signups`.

## Deploy

Static GH Pages site. CNAME → `signup.cannacrypted.com`.
