# Amplitude Data Governance Workshop

An interactive, single-file HTML workshop for Amplitude CSAs to run live data governance sessions with customers.

## Overview

The workshop guides teams through the key pillars of Amplitude data governance in a structured, 7-step flow. Everything runs in the browser — no server, no dependencies, no install.

## How to Use

1. Open `governance-workshop.html` directly in any modern browser
2. In **Step 3 — Connect to Live Project**, paste the customer's Amplitude Data tab URL to unlock live links throughout the workshop
3. Walk through each step with the customer team

## Workshop Steps

| # | Tab | What it covers |
|---|-----|---------------|
| 1 | Overview | Workshop goals, governance pillars, and what good governance looks like |
| 2 | Governance Model | Centralized vs. federated vs. hybrid — pick the right model and generate a checklist |
| 3 | Taxonomy Design | Style guide builder — naming conventions, object-action pattern, property standards |
| 4 | Tracking Plan | Four sub-tabs: Branches (4.1), Schema Settings + Observe (4.2), Virtual Data Extensions (4.3), Transformations (4.4) |
| 5 | Governance Controls | Data Access Controls — blocking, dropping, PII tagging, event lifecycle |
| 6 | Data Assistant Agent | Today's Data Assistant capabilities + link to launch the Data Assistant Agent in the customer's project |
| 7 | Workshop Activity | Live-fill governance process table, review cadence, and post-workshop checklist |

## Loading Customer Events (Bookmarklet)

The workshop includes a bookmarklet that loads the customer's live event list directly from their Amplitude project — no API keys required.

**Setup (one-time per browser):**
1. Paste the customer's Data tab URL in Step 3
2. Drag the generated **"📊 Get Amplitude Events"** bookmark to your bookmarks bar

**Each session:**
1. Open the customer's Amplitude project in another tab
2. Click the bookmarklet — it reads the event list and posts it back to the workshop
3. The style guide checker and taxonomy analysis populate automatically

## Live Links Generated from the Data Tab URL

When a Data tab URL is entered in Step 3, the workshop automatically constructs:

| Link | Purpose |
|------|---------|
| **Open in Amplitude Data** | Direct link to the customer's tracking plan |
| **Open Data Assistant** | Deep-links to `Data → Assistant` for the project |
| **Open Data Assistant Agent** | Launches the Data Assistant Agent in Analytics for the org |

## Configuration

`CUSTOMER_CONFIG` at the top of the `<script>` block lets you pre-fill customer details before a session:

```javascript
const CUSTOMER_CONFIG = {
  customerName: "Acme Corp",      // Shown in the header
  hasAmplitudeData: true,         // Show/hide Data-specific content
  hasTaxonomyAgent: true,         // Show/hide agent checklist items
  hasCDP: false,                  // Show/hide CDP-related callouts
};
```

## Deployment

The workshop is a single static HTML file. Host it anywhere that serves static files:

- **GitHub Pages** — commit the file to a repo and enable Pages (recommended for sharing with teams)
- **Lovable** — drag and drop for a hosted shareable URL

No build step, no dependencies.

## File Structure

```
governance-workshop.html   ← everything is here
README.md
```
