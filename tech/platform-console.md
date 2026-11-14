# Platform console checklist

**You are:** a SoBoss platform admin, the person who brings restaurants onto the system.
**You need:** the platform console link and an admin login with MFA. Use `TEST` in the name of every tenant, plan and template you create. Never suspend or change the standard test restaurant while others are testing it.

## Signing in

| ID | Check | Pass when |
|---|---|---|
| PC-01 | Sign in with MFA: a wrong code, then the right one | The wrong code is refused. The right code gets you in. There is no way in without MFA. |
| PC-02 | Leave the console idle | A countdown warns you, then signs you out. |
| PC-03 | A restaurant owner's login on the console; the console's address from a network that is not allowed | Both refused. |

## Bringing a restaurant on

| ID | Check | Pass when |
|---|---|---|
| PC-04 | Create a tenant with the wizard: organisation `TEST Spice Garden`, a brand, an outlet, an owner, a role template, a settings template and a tax preset | One tenant is created. The owner receives their invitation. |
| PC-05 | Refresh or double-click on the wizard's last step | No duplicate tenant, outlet or owner. |
| PC-06 | The new owner signs in to the dashboard | They are made to set up an authenticator app. They see their own empty restaurant, with helpful first steps, and nothing of any other tenant. |
| PC-07 | The new tenant's roles, settings and taxes | They match the templates and the tax preset chosen. GST 5% is two parts of 2.5%. |
| PC-08 | The new outlet's invoice code | Suggested from the outlet's name, 3 characters, unique in the organisation, and editable until the outlet's first bill. |
| PC-09 | Wizard validation: a wrong PAN or GSTIN, a phone with letters, an owner email already used | Each is refused with a clear message. |

## Managing tenants

| ID | Check | Pass when |
|---|---|---|
| PC-10 | Search tenants by organisation name, legal name and PAN, in any letter case | The right tenants are found, including ones not on the first page of the list. |
| PC-11 | Open a tenant | Its outlets, plan, status and owner are right. No customer names, bills or sales are shown. |
| PC-12 | Suspend `TEST Spice Garden` | Its dashboard sign-in shows a clear "suspended" message. Note what its till does: record it. Other tenants are unaffected. |
| PC-13 | Reinstate it | Everything works again, with its data intact. |
| PC-14 | Record a subscription payment, and look at what is due | The balance and the next due date update. |
| PC-15 | Start support access to a tenant, with a reason | A reason is required. Access is time-limited. The tenant's own audit trail shows that SoBoss support looked, who and when. |
| PC-16 | Request a data export for a tenant | It completes, and is available only to the people allowed. |

## Platform-wide settings

| ID | Check | Pass when |
|---|---|---|
| PC-17 | Plans: view, create `TEST Plan`, edit | Saved. A new tenant on that plan gets its features. |
| PC-18 | Feature flags: switch one off for `TEST Spice Garden` | That tenant's apps hide or refuse the feature. Other tenants are unaffected. Switch it back. |
| PC-19 | Tax presets, role templates, settings templates: view, create a `TEST` one, edit | Saved. A tenant created afterwards starts with them. Existing tenants do not change. |
| PC-20 | Platform config and fleet health | Current, readable information: which tills are online, their versions, when each was last seen. No secrets shown. |
| PC-21 | Everything you changed | Recorded with your name and the time. |
