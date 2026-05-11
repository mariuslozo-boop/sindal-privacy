---
title: Sindal Chrome Extension — Privacy Policy
---

# Sindal Chrome Extension — Privacy Policy

_Last updated: 2026-05-11_

## Who we are

The Sindal Chrome extension is an internal tool for staff of Sindal Autoophug
(a Danish auto-recycler). It coordinates a parts-lookup workflow across three
third-party websites the staff already use, plus a local stock-file helper.

**Contact:** mariuslozovskis@gmail.com

## What the extension does

The extension assists with one workflow: moving a vehicle identifier (VIN) and
an original-equipment part number (OE) between three trade websites
(`au2web.dk`, `partslink24.com`, `appmain.nemdele.dk`) and, optionally, the
user's own local stock file via a native-messaging helper. It is **not**
intended for the general public.

## Data we collect

### 1. Telemetry (opt-in)

If the user picks an identity in the popup, the extension sends one anonymous
event per workflow step to a Google Apps Script endpoint owned by the
extension author. Each event contains only:

- the workflow step name (e.g. `au2web_capture`, `partslink24_vin_fill`,
  `nemdele_send`),
- a short random flow-correlation id,
- the user-chosen display name (e.g. a first name),
- the local timestamp.

**No** VIN, OE number, vehicle data, page content, IP address, browsing
history, or any other identifier is sent. If the user does not pick an
identity, **no telemetry is sent at all**.

### 2. Local-only data

The extension stores the following in `chrome.storage` on the user's own
computer. This data never leaves the device:

- the selected telemetry identity,
- the last opened popup pane,
- the last selected stock-report filename,
- a transient brand-pick state used by the Partslink24 content script.

### 3. Native-messaging host (local helper)

The companion helper `dk.sindal.helper` runs on the user's machine and reads
a local Excel stock file (`stock.xlsx`) and PDF reports the user selects. All
data read by the helper stays on the local machine; nothing is uploaded.

## How data is used

Telemetry is used solely to measure whether the workflow is being completed
end-to-end. It is **not** sold, shared with third parties, used for
advertising, used for profiling, or used to determine creditworthiness or
lending eligibility.

## Where data is stored

Telemetry events are written to a Google Sheet owned by the extension author
and accessed only by Sindal staff for internal review. Events are retained
indefinitely and can be deleted on request to the contact email above.

## What we do NOT collect

- Personal identifiers beyond the user-chosen display name
- VINs, license plates, OE numbers, or any parts data
- Page content from au2web, Partslink24, or NemDele
- Authentication credentials or session cookies
- IP addresses or geolocation
- Browsing history outside the three host-permission domains
- Health or financial information

## Permissions and why we need them

- `storage` — saves the local preferences listed above.
- `tabGroups` — coordinates the workflow tabs in a single Chrome group.
- `nativeMessaging` — communicates with the local helper described above.
- Host permission on `*.partslink24.com`, `webkat.au2web.dk`,
  `appmain.nemdele.dk` — required to inject the workflow content scripts.
- Host permission on `script.google.com` and `script.googleusercontent.com`
  — required for the opt-in telemetry endpoint.

## Changes to this policy

Material changes will be reflected by updating the "Last updated" date at the
top of this page.

## Contact / removal requests

Email **mariuslozovskis@gmail.com** to request deletion of any telemetry
events tied to your display name.
