---
title: Measurements in the cloud
linkTitle: Measurements
weight: 50
description: >-
  View, export, complete and delete measurement data in the cloud.
---

A measurement appears in SPL Cloud as soon as its **Cloud Uplink** is switched on in SPL Sense and the instance has
internet. New measurements are listed first under the independent measurements on the overview.

## The measurement page

Below the title, a line shows the essentials: job, owner, the instance currently measuring (with state), and whether Pro
is active.

- **Live:** while the measurement is running, you see the current 1-second values, with an active leveler also gain
  reduction and correlation. If the instance stops reporting, **Connection lost** is shown with the last contact.
- **Days, chart, deviations and events:** the same as in SPL Sense, see
  [Evaluating measurement data]({{< relref "/docs/spl-sense/measurement-data" >}}).
- **On the side:** access (who sees the measurement), Pro, pictures and the other measurements of the same job.

If something about the measurement changes in SPL Sense, for example the offset, the page updates itself.

## Reports and exports

| What | Where | |
|---|---|---|
| CSV of the day | **CSV** button at the day | free |
| Day report (PDF) | **PDF** button at the day | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |
| CSV of all days (ZIP) | Menu **Measurement** › **Export all measurement days to CSV** | free |
| Day report with deviations | Menu **Measurement** › **Open day report with deviations** | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |
| Pictures report | Menu **Measurement** › **Open pictures report** | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |

The reports carry the logo of the organization that owns the measurement.

## Completing

Menu **Measurement** › **Complete measurement**. After that, the cloud no longer accepts new data, even if SPL Sense
keeps measuring. Data up to the time of completion that is still on its way still arrives.

If you complete the measurement in SPL Sense, it is also completed in the cloud. It is reopened in SPL Sense or with
[remote control]({{< relref "/docs/spl-cloud-pro/remote-control" >}}).

## Deleting

You delete a completed measurement in the menu **Measurement** › **Delete measurement**. It is permanently removed from
the cloud. The measurement is kept in SPL Sense.

## Who sees the measurement

| Who | May |
|---|---|
| Owner of the measurement (person or all members of the organization) | everything: view, grant access, complete, delete |
| Owner of the job, if different | view, see [Different owners]({{< relref "jobs#different-owners" >}}) |
| People with [read access]({{< relref "read-access" >}}) | view |
| Recipients of a [shared link]({{< relref "/docs/spl-cloud-pro/shared-links" >}}) | view, without an account |
