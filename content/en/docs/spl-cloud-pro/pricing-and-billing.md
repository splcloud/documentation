---
title: Pricing and billing
linkTitle: Pricing and billing
weight: 10
description: >-
  What Pro costs, how to activate it and how it is billed.
---

## The principle

- Pro applies **per measurement**. You activate it for a single measurement or for all measurements of a job.
- You pay **per measuring day**. A measuring day counts if the measurement recorded more than one hour of data on that
  day. The measurement's day boundary is decisive.
- There is a **cap** per measurement and year. Once reached, Pro continues free of charge until the end of the
  measuring year.
- No subscription, no base fee. A measurement without data costs nothing.

## Prices

You find the current prices on [spl.swiss](https://spl.swiss/products/cloudpro). The model:

- The first measuring days of a measurement cost more; from the 7th measuring day, a lower daily price applies.
- There is a cap per measurement and **measuring year**. Once reached, Pro continues free of charge until the end of the
  measuring year.
- The measuring year lasts 365 days from the measurement's first measuring day (if it has no data yet: from the day of
  activation). After that, a new measuring year begins and counting starts again at the first day.
- Prices exclude VAT.

Before each activation, SPL Cloud shows the price and, if data has already been recorded, the exact amount. If prices
change, a measurement that is already activated keeps the price at the time of its activation.

## Prerequisite: payment method

Before you activate Pro, the owner of the measurement needs a payment method and a billing address. The billing address
is needed for VAT.

| Owner of the measurement | Where to set up | Who |
|---|---|---|
| you personally | **Settings** › **Payment** | you |
| an organization | organization page › **Billing** | an owner of the organization |

For Pro on a job, the owner of the job needs the payment method.

1. Choose the **Billing currency**: CHF or EUR. It cannot be changed afterwards.
2. Click **Set up payment**. Payment is handled by the payment service Stripe; there you choose the payment method and
   enter the billing address. You can see there which payment methods are available.
3. Back in SPL Cloud, **Payment method and billing address saved.** is shown.

The invoice is addressed to the person or organization that owns the payment method. **Manage billing** opens your
invoices at Stripe and lets you change the payment method. For an organization, the **Billing language** in the
organization details determines the language of the invoices.

## Activating Pro

### For a measurement

1. Open the measurement. On the side, **Get Pro!** shows the included features and the price.
2. Click **Activate Pro** and confirm.

### For a job

On the job page, **Activate Pro for the job**. All measurements of the job are then Pro, including those added later.
Each measurement is still billed individually by its measuring days, with its own cap.

The **owner of the job** pays, also for measurements that belong to someone else. Measurements for which their owner has
already activated Pro directly continue to be paid by that owner. Details under
[Different owners]({{< relref "/docs/spl-cloud/jobs#different-owners" >}}).

### Free test hour

The first time you activate a measurement directly, you have one hour to try it out. There is no test hour when
activating via the job. If you deactivate Pro within that hour, it costs nothing, not even for days already recorded.
While the test hour is running, the measurement shows **Free test hour running**.

### Retroactive billing

Pro is billed from the **measurement's first measuring day**, not from the time of activation. If you activate Pro for
a measurement that has been running for three days, those three days count. SPL Cloud shows you the exact amount before
activation.

## Deactivating Pro

With **Deactivate Pro** on the measurement or **Deactivate Pro for the job** on the job:

- The Pro features are locked immediately. Shared links stop working, alarms are no longer evaluated.
- Amounts already accrued are billed with the next invoice. There is no refund.
- Further measuring days are no longer counted. The measurement continues recording normally.
- Measurements that were activated directly stay active when you deactivate Pro for the job.

### Activating again

If you activate Pro again later, the measuring year continues seamlessly as if there had been no break. **Measuring days
from the break are counted retroactively.** There is no test hour anymore; billing starts immediately. Switching off and
on repeatedly therefore saves nothing.

## Billing

Billing happens once a month, on the last day of the calendar month, for all measuring days accrued in that month. The
stored payment method is charged automatically.

If the charge fails, the payment service retries several times. If payment fails definitively, the Pro features of the
affected measurements are locked until the payment is settled.

## Keeping an eye on costs

- **Accrued costs** in the payment settings: all Pro measurements with their costs in the current year.
- **License details** of a measurement (via **View details** at Pro): measuring year, billable measuring days, progress
  towards the cap, amounts already billed, billing history and all measuring days with their recorded time.
- **License details** of a job: total across all its measurements.

Only people who may manage the job or measurement see the costs.
