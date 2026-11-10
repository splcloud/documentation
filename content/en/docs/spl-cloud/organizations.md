---
title: Organizations and roles
linkTitle: Organizations and roles
weight: 20
description: >-
  What organizations are for and what owners and members may do.
---

## Why organizations?

Everything in SPL Cloud has an **owner**: measurements, jobs and SPL Sense instances. The owner is either a person or an
**organization**.

An organization is a group of people who access measurements together: a company, a club, a festival or an authority.
All members see the organization's measurements, and when someone leaves the company, the data stays with the
organization.

A person can be a member of several organizations, for example as a freelance technician working for several companies.
When creating a job or registering an instance, you choose who should own it.

## Roles

| | Owner | Member |
|---|---|---|
| See the organization's measurements and jobs | ✓ | ✓ |
| Create jobs, assign measurements | ✓ | ✓ |
| Register SPL Sense instances for the organization | ✓ | ✓ |
| Grant read access | ✓ | ✓ |
| Remote control the organization's instances (with Pro) | ✓ | ✓ |
| Add and remove members, change roles | ✓ | |
| Change the organization's name, address and logo | ✓ | |
| Manage payment method and invoices | ✓ | |

An organization always has at least one owner.

Anyone who should only view data, for example an organizer or an authority, does not become a member but gets
[read access]({{< relref "read-access" >}}).

## Creating an organization

1. **Settings** › **Create Organization**.
2. Enter **Name**, address and **E-Mail Address**. The **Billing language** determines the language of invoices and
   payment pages.
3. **Save**. You are now the owner of the organization.

## Managing members

On the organization's page:

1. **Add Member**.
2. Search for the person by email address. They must already have an SPL Cloud account.
3. Choose the **Role**: **Owner** or **Member**. **Save**.

Clicking a member opens it: change the role or **Remove Member**.

## Logo

The organization's logo appears in the PDF reports of its measurements. **Upload logo** (image file up to 5 MB),
**Change logo** or **Remove logo**.

## Typical setups

**Individual:** a technician with her own sensor and laptop, without an organization. Instance and measurements belong
to her personally. She gives the organizer read access to the measurement.

**Technical company:** the company has an organization; all laptops and Raspberry Pis are registered as instances of
the organization. All employees are members and see all measurements. At a festival, a job groups the measuring points;
the authority gets read access to the whole job, the operator of a stage to their measurement.

**Rented devices:** if a device is rented out and should belong to the renting company for the rental period, change
the owner of the instance, see [SPL Sense instances]({{< relref "instances#changing-the-owner" >}}).
