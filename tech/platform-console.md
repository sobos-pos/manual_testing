# Platform console checklist

**You are:** a SoBoss platform admin. You need the platform console link and an admin login with MFA.

| ID | Check | Pass when |
|---|---|---|
| PC-01 | Sign in with MFA. Wrong code, then right code. | A wrong code is refused. The right code gets you in. |
| PC-02 | Tenants list: search and open a tenant | Search works. Details are correct. |
| PC-03 | Create a new tenant (restaurant, outlet, owner) with the wizard | One tenant is created. The new owner can sign in and start setting up. |
| PC-04 | Refresh or double-click at the end of the wizard | No duplicate tenant. |
| PC-05 | Plans: view, create, edit | Saved. Applied to new tenants as expected. |
| PC-06 | Feature flags: switch one off for a test tenant | That tenant's apps hide or block the feature. Others are unaffected. |
| PC-07 | Tax presets: view and edit | New outlets get the right tax setup. |
| PC-08 | Role and settings templates | New tenants start with the template's roles and settings. |
| PC-09 | Config and health pages | Show current, readable information. No secrets are shown. |
| PC-10 | A restaurant owner tries to open the console | Refused. |
