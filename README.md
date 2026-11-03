# Approval-Based Multi-Channel Social Publishing Automation

**Make.com · Facebook Pages · Instagram Business · HTTP / API integrations · Human-in-the-loop review**

> **Case study:** A real, self-directed business automation project for SnackyBara. Not a claim of paid client work. The images below come from the owner's Make.com workspace and a public Facebook post, selectively cropped to exclude private scenario inputs and run identifiers.

![Simplified approval-based workflow architecture](assets/workflow-overview.svg)

## Business challenge

Publishing a small business's approved social content manually across channels requires repetitive work and different platform-specific steps for photos, Reels, and Stories. When a destination fails, automatically resending to *all* destinations risks duplicates.

The goal was to maintain **human approval of content** while simplifying the technical process of publishing, checking outcomes, and handling issues per destination.

## Solution

I configured two active on-demand Make.com scenarios for publishing already-approved material:

- **Posts / Reels:** Conditional media and destination routes with Facebook Pages and Instagram Business modules, Make routers/filters, and HTTP/API requests. The configuration also includes additional Google Business Profile and TikTok routes. Their presence is not evidence of completed tests on every destination.
- **Stories:** Image/video-specific publishing paths for Facebook and Instagram Stories, built with HTTP requests, branch filters, and return responses.

Publishing is initiated from an upstream approval workflow; these scenarios are **not** a fully unsupervised marketing AI and **not** independent posting timers.

## Implementation details

| Challenge | Design approach |
|---|---|
| Different social-media formats | Distinct feed/Reel and Story scenarios; route by destination and media type |
| Approval and brand control | Owner reviews content before an approved publish request is sent |
| API/platform differences | Use native Facebook/Instagram modules where applicable and HTTP API requests for selected paths |
| Partial failures | Return destination results and provide conditional review / retry paths where supported |
| Observability | Status-handling and response modules expose the workflow outcome to the caller |

The scenario configuration has validation and recovery branches. **I do not claim exactly-once posting or guaranteed idempotency**, since those would require targeted end-to-end tests for each destination.

## Project evidence

### 1. Publishing scenario architecture

![Sanitized Make.com posts scenario overview](assets/make-posts-route-overview-sanitized.png)

*A zoomed-out view of the active posts-and-Reels scenario, cropped to remove the browser address bar and unrelated interface. The conceptual diagram above explains its major stages more clearly than the compressed Make screenshot.*

### 2. Example Story scenario execution

![Sanitized story scenario run](assets/make-stories-run-sanitized.png)

*Selected portions of a November 3, 2026 Make.com run showing its started timestamp and green module-status indicators. The screenshot excludes the execution ID and API request details. This demonstrates a recorded run; it does not, alone, establish a matching public Story or overall monthly success rate.*

### 3. Public publication example

![Example Facebook publication](assets/facebook-publication-example.png)

*An example of a social post published on the SnackyBara Facebook Page. This image and the Story execution screenshot are separate examples; they have not been correlated as one identical transaction.*

## Verification and honest results

The connected Make account showed the two publishing scenarios active on November 3, 2026. The scenario blueprints and historical execution records were inspected. **No independently verified measure of hours saved, sales lift, or total successful unique posts is claimed.** This example demonstrates architecture and operational implementation, not measured business ROI.

## What I can deliver for a client

- Connect approval workflows to supported SaaS publishing or business-operations actions.
- Design Make.com scenarios with routers, filters, API calls, and status responses.
- Audit existing low-code automations for wrong-route, unsupported-format, and partial-error problems.
- Build maintainable integrations for forms, spreadsheets, business systems, or online services, with scoped delivery criteria.

Each client project depends on the destination's API permissions, credentials, requirements, acceptance testing, and agreed support scope.

## Related web project

I also built a small-business website for SnackyBara using **Astro 7, Tailwind CSS 4, and Vercel deployment configuration**.

- **Owner-provided website:** https://snackybara-website.vercel.app/
- **Source repository:** https://github.com/Okz-kun/snackybara-website

The website repository has Home, Menu, About, Gallery and Contact pages. Its contact form source still contains a placeholder Formspree ID; live form submission remains unverified and should be fixed or openly disclosed before offering the site as a fully functional client demo. The deployed URL could not be independently fetched in this review environment.

## Privacy

This case study does **not** contain production Make blueprints, access tokens, live webhook URLs, private account IDs, authentication payloads or confidential HR/client information. Never share the original uncropped run screenshot or publicly share production Make scenario pages without a full secrets and mapping review.

---

**Portfolio status:** Sanitized portfolio case study prepared for publication. No production Make blueprint or credentials are included.
