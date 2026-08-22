---
title: Privacy Policy — Flow Metrics & Forecasting
---

# Privacy Policy — Flow Metrics & Forecasting

> **Draft — not legal advice.** The data-practice descriptions below (what the app
> reads, stores, and does not read/store) were verified directly against the app's
> source code, not assumed or templated — see the "How we verified this" note at the
> end of the relevant section for the exact mechanism. The legal framing (GDPR role,
> retention language, your-rights section) is a reasonable starting draft, not a
> substitute for review by a lawyer qualified in Greek/EU data protection law before
> this is relied on. Placeholders in `[BRACKETS]` will be filled in before this notice
> is removed.

**Effective date:** [DATE OF PUBLICATION]
**Last updated:** 2026-08-22

## 1. Who we are

Flow Metrics & Forecasting ("the App") is developed and published by:

**Pathways Consulting Services P.C. (Ι.Κ.Ε.)** — **[pathways](https://yourpaths.eu)**
Registered in Greece
[REGISTERED ADDRESS]
Company registration (ΓΕΜΗ) number: [GEMI NUMBER]
VAT / ΑΦΜ: [VAT NUMBER]
Contact: **[info@yourpaths.eu](mailto:info@yourpaths.eu)**

We are the developer/vendor of the App, distributed via the Atlassian Marketplace and
installed on your own Atlassian Jira Cloud site.

## 2. What the App does, in one paragraph

The App reads issue and workflow data from a Jira project you choose to install it on,
and turns it into flow-metrics charts (cycle time, cumulative flow, aging work,
forecasts) that are rendered **inside Jira**, for users of that same Jira site. It does
not have its own website, user accounts, or login — access is entirely governed by your
existing Jira permissions.

## 3. What data the App accesses, and why

| Data | Why | Read as |
|---|---|---|
| Issue fields: **summary, status, issue type, created date, resolution date, updated date** | To compute cycle time, throughput, cumulative flow, and aging metrics | The viewing user's own Jira permissions |
| Issue **status change history** (changelog): status transitions and their timestamps | Cycle time and aging are measured from when an issue *actually* moved between statuses | The viewing user's own Jira permissions |
| **Board configuration** (name, type, saved filter) | To determine which issues belong to the board being viewed | The App's own identity (so any user who can see the board gets correct results, not just board admins) |
| **Jira site timezone** | So "what counts as a day" matches what Jira itself reports, identically for every viewer | The App's own identity |

**How we verified this:** the App's Jira API layer explicitly restricts every Jira
issue request to the field list above — the App does not request Jira to return any
other issue field.

## 4. What the App deliberately does **not** access

- **No assignee, reporter, or any user-identifying field.** The App's Jira permissions
  intentionally exclude the scope Jira requires to resolve user profile information.
  The App's code never reads, parses, stores, or displays an assignee, reporter,
  watcher, or commenter, on any issue.
- **No issue description, comments, or attachments.**
- **Changelog "author" data is never used, even though Jira's API technically includes
  it.** Jira's changelog format includes who made each change alongside what changed.
  The App's code extracts only the *status* field change and its timestamp from each
  changelog entry — the author field is present in the raw network response but is
  never read, stored, or rendered anywhere in the App, including in the per-issue
  "raw changelog" detail view (which shows only the App's own extracted from/to/
  timestamp data, not Jira's raw response).

## 5. Where your data goes

**Nowhere outside Atlassian.** The App has no servers of its own, makes no calls to
any third party, and uses no analytics, advertising, or tracking service of any kind.
All Jira API calls happen either directly from your browser (as you) or from the App's
backend function running on Atlassian's own Forge platform (as the App) — both stay
entirely within Atlassian's infrastructure. This is why the App qualifies for
Atlassian's **"Runs on Atlassian"** program, which specifically certifies that an app
has no external network egress.

We (pathways) never receive, see, or have access to your Jira issue data. There is no
database of ours that your data passes through.

## 6. What the App stores, and where

- **Project-level configuration**, stored in Atlassian's own Forge key-value storage
  (physically hosted by Atlassian, not by us): your chosen status-to-stage mapping,
  saved date-range preference, and any issues you've manually excluded from metrics.
  This is configuration **about how to display your board**, not your issue content —
  no issue summaries, descriptions, or user data are stored here. It is shared
  per-project (visible to any project member), not tied to an individual user account.
- **A local browser cache** (IndexedDB, inside your own browser, on your own device):
  a copy of the same limited issue fields listed in §3, kept only to make reopening the
  App faster. This never leaves your browser and is not something we have access to.

## 7. How long we keep data, and what happens if you uninstall

Because all storage described in §6 lives in Atlassian's own Forge platform (not ours),
data lifecycle is governed by Atlassian's platform policy, not a policy we control:
uninstalling the App marks its stored configuration for deletion, following Atlassian's
standard Forge hosted-storage retention/deletion process (see [Atlassian's Forge
storage data lifecycle
documentation](https://developer.atlassian.com/platform/forge/storage-reference/hosted-storage-data-lifecycle/)
for Atlassian's current, authoritative retention timeline — subject to change on
Atlassian's side, not ours). We do not separately retain a copy anywhere.

## 8. Your rights

Because the App does not process personal data about identifiable individuals (see §4),
there is generally very little personal data for us to act on. To the extent GDPR or
similar law applies to any data connected with your use of the App, you can contact us
at **[info@yourpaths.eu](mailto:info@yourpaths.eu)** to ask about access, correction,
or deletion, and we will respond consistent with applicable law. For your underlying
Jira data itself, your Jira site administrator (your organization) is the controller —
the App only reads it under permissions your organization already granted.

## 9. Sub-processors / third parties

**Atlassian** (as the hosting platform for Forge, the infrastructure the App runs on)
is the only third party involved, and it is the platform your organization has
independently chosen and contracted with by using Jira Cloud. We do not add any other
sub-processor, vendor, or third-party service.

## 10. Children's privacy

The App is a business tool for use within an organization's Jira instance and is not
directed at, or knowingly used by, children.

## 11. Changes to this policy

We will update the "Last updated" date above when this policy changes, and post the
updated version at the same location. Material changes will be reflected in the
Atlassian Marketplace listing.

## 12. Contact

Questions about this policy or the App's data practices:
**[info@yourpaths.eu](mailto:info@yourpaths.eu)**

---

Published by **[pathways](https://yourpaths.eu)** (Pathways Consulting Services P.C.)
· [EULA](./eula.html) · [Back to legal index](./)
