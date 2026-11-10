---
title: Jobs with several measuring points
linkTitle: Jobs
weight: 40
description: >-
  Group several measurements into one job.
---

A **job** groups several measurements that belong together: all stages of a festival, the measuring points of a
construction site or a club with a main and a side room. Each measuring point remains a separate measurement with its
own sensor, value profile and data. The job shows them together and lets you set access, Pro and alarms for all of them
at once.

Jobs only exist in SPL Cloud; SPL Sense only knows measurements.

## Creating a job

1. On the overview, **Create new job**.
2. **Name**, for example "Openair 2026".
3. **Location** (optional).
4. **From** and **To**: the period. It determines when the job moves to the
   [archive]({{< relref "account-and-interface#archive" >}}), namely ten days after the end date.
5. **Owner**: you personally or an organization. The owner cannot be changed later.
6. **Save**.

## Assigning measurements

On the job page, in the menu **Job** › **Manage Measurements**:

- **Assign Measurements**: choose measurements that do not yet belong to a job.
- **Remove** takes a measurement out of the job. It becomes independent again.

**Finish Manage Measurements** ends editing.

Each measurement belongs to at most one job.

## Different owners

Job and measurements can belong to different owners. Typical case: the organizer keeps the job "Openair 2026" in their
organization, and a technical company measures a stage with its own laptop. The measurement then belongs to the
technical company (the owner of the instance that uploads it), the job to the organizer.

### Assigning

Only someone who may do **both** can assign a measurement: manage the job and manage the measurement. In practice, this
is a person who is a member of both organizations. The measurement keeps its owner when assigned.

### Who may do what

In the example, **A** is the technical company (owner of the measurement) and **B** the organizer (owner of the job).

| | A: owner of the measurement | B: owner of the job |
|---|---|---|
| View the measurement, reports and exports | ✓ | ✓ |
| Complete or delete the measurement, add pictures | ✓ | |
| Upload data (only instances of A) | ✓ | |
| [Remote control]({{< relref "/docs/spl-cloud-pro/remote-control" >}}) of the instance | ✓ | |
| Grant [read access]({{< relref "read-access" >}}) to this measurement | ✓ | |
| Grant read access to the whole job (also applies to A's measurement) | | ✓ |
| Remove the measurement from the job | | ✓ |
| Activate Pro for the measurement (A pays) | ✓ | |
| Activate Pro for the job (B pays, also for A's measurement) | | ✓ |
| See costs and license details of the job | | ✓ |
| [Alarms]({{< relref "/docs/spl-cloud-pro/alarms" >}}) for the whole job | | ✓ |
| Alarms only for this measurement (overrides those of the job) | ✓ | |
| [Shared link]({{< relref "/docs/spl-cloud-pro/shared-links" >}}) to the measurement (needs Pro on the measurement) | ✓ | |
| Shared link to the job (needs Pro on the job, also shows A's measurement) | | ✓ |

"A" and "B" each stand for the person or all members of the organization that owns the measurement or job.

### Pro with different owners

- If **B** activates Pro for the job, **B** pays for all measurements in it, including A's, in B's currency.
- If **A** has already activated Pro directly on the measurement, that stays: A continues to pay for this measurement.
- If A deactivates the direct activation while the job is Pro, the measurement stays Pro via the job.

See also [Pricing and billing]({{< relref "/docs/spl-cloud-pro/pricing-and-billing" >}}).

## Editing and deleting

**Edit** changes name, location and period. **Delete Job** is only possible when no measurements are assigned to it
anymore.

## Example: festival with three measuring points

A technical company looks after a festival with a main stage, a tent and a measuring point at the nearest residential
building.

1. Three laptops with SPL Sense are registered as instances of the company's organization.
2. On each laptop, a measurement with cloud uplink is created: "Main stage", "Tent", "Neighbourhood".
3. In the cloud, the job "Openair 2026" is created with the festival period, and the three measurements are assigned.
4. The authority gets [read access]({{< relref "read-access" >}}) to the whole job, the operator of the tent only to
   their measurement.
5. Optionally: [Pro]({{< relref "/docs/spl-cloud-pro" >}}) for the whole job, for example for
   [alarms]({{< relref "/docs/spl-cloud-pro/alarms" >}}) to the technicians or a shared link for the organizer.
