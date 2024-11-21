# State of authentication in Decidim and proposal on how to improve it

## Challenge 
With Decidim, we inherit a two-part authentication system: accounts and authorizations.

- An account is a user — they have a name, a username, an email, and a password.
- An authorization is permission to perform an action on the platform. Generally, authorization is obtained if one is part of a "census," enters a phone number, provides an ID card photo, or something else that certifies one’s identity.

However, neither accounts nor authorizations have been left untouched and we have modified them since we started using Decidim (and we’re not the only ones doing this). For the account, we've created [extra sign up fields](https://github.com/OpenSourcePolitics/decidim-module-extra_user_fields.git) that allow adding fields to the registration or [friendly signup](https://github.com/OpenSourcePolitics/decidim-module-friendly_signup.git) that eliminates the need to enter the password multiple times, choose a username, etc. Regarding authorizations, we have repurposed them to collect additional information from project holders, which we then collected via our BI and visualization tool, required [phone number verification](https://github.com/OpenSourcePolitics/decidim-module_phone_authorization_handler), etc.

These module customizations mainly stem from client requests who want to collect information about users or restrict/secure certain actions on the platform. It’s a legitimate request, though it often leads to poor UX and a lot of technical debt. We have several modules dedicated to different versions of authentication, and some of these modules are divided into several radically different branches. Here are some issues that these modules face:

- [Half-sign-up](https://github.com/OpenSourcePolitics/decidim-module-half_sign_up.git) is customized differently for two different clients, and we proposed the module to several clients who refused it because it created ghost or incomplete accounts;
- With [friendly sign-up](https://github.com/OpenSourcePolitics/decidim-module-friendly_signup.git), we faced issues where people did not confirm their email address yet interacted with the platform;
- Each SSO implementation takes us a lot of time;
- We rarely manage different user roles on Decidim;
- We need Metabase to retrieve information;

Here are some requests we can't answer:
- mandatory or non-mandatory fields at registration;
- configuration of custom fields by the clients themselves.

Therefore, the situation with authentication is not optimal despite some very nice advancements, particularly friendly signup and extra sign-up fields. The major challenge remains how to accommodate numerous different authentication methods without creating a unique module for each platform, without systematically refusing all client needs, and without sacrificing user experience.

The response we propose results from mapping several client requests that we've seen as a team, the extreme cases being an engineering school, a large French city and one of the most iconic cities in North America, but these are not the only cases where we had to do custom authentications. Here are the three examples:

1. **Engineering school** : If you sign up with a student SSO from a specific IMT branch, you can, for example, vote or submit proposals in certain spaces/functions but not others.
	- In Decidim-specific terms: Based on this SSO information, you would be assigned to a private assembly based on your status OR you can vote or submit a proposal in a functionality only if you have a status.
2. **French city** :
	- To register on the platform, you do so with an email address, but if you want to vote, only a phone number is required. However, if you register with your email address, you are also asked for your phone number.
3. **North American city** :
	- You can vote via email and SMS without having a username, but if you want to submit a proposal, you need a username.

These examples inspire these **user stories**:
- As an administrator, I want to be able to condition participation in certain spaces or the ability to perform certain actions to user criteria obtained either by declaration or verification (e.g., SSO information).
- As an administrator, I want to be able to ask users for additional information to make participation more representative, reliable, and contextualized.
	- I don't want to ask for everything all at once as that would discourage registration.
		- I want to ask for information at the most pertinent moment.
		- I even want to offer registration on the platform without an email address.
	- However, I also want to keep the possibility of not asking for any information at all and enable anonymous participation.
- As a user, I want to be able to participate easily without concerns about providing too much personal data.


## Solution

Satisfying all these user stories is not straightforward: there are as many authentication methods as participation platforms, and we need to optimize both the user experience and administrative flexibility. The proposed approach can be summarized with two words:

**Minimal**
- We ask the user only what the administrator needs to reconnect;
Requesting the bare minimum limits the load of registration and connection as much as possible.

**Progressive**
- We ask for information gradually, only when it is truly needed;
- We store this information in the user profile so they don’t have to provide it again.
The question now is what would it look like on Decidim?

Let’s start with the user side:
- Registration would remain more or less the same except for two major improvements — it would happen entirely in a modal (with a warning on mobile screens), and according to the preferences and obligations of the administrators, the forms would be different, though we would want them to be as simple as possible.

![Image](https://github.com/user-attachments/assets/a1ab0ef1-55d1-464e-ba58-94fa67a1036f)

- When the user wants to perform an action that requires more information or verification, a new modal would appear asking them to fill in the missing information.

And then for the admin:
- A page to configure minimal signup and SSO (in global settings):
	- The minimal signup to configure would be a choice between email, SMS, or both, and additionally a set of fields configurable by the administrator;
![Image](https://github.com/user-attachments/assets/a252143c-ef53-4f01-8c8a-77afc0d726c0)
	- The SSO configuration would be done from a library of existing SSOs by checking boxes for the data to be retrieved and added to the user profile or their general data.
![Image](https://github.com/user-attachments/assets/9625f7d8-db48-4265-81aa-da22580a0ffc)
- In each management page of a consultation, assembly, or feature, the possibility to add criteria to view (only in the case of assemblies) or perform actions.
![Image](https://github.com/user-attachments/assets/aa760d29-b824-431d-b5e0-12c34a32bf2a)

### FAQ

**How do we manage anonymous participation?**
- Everything will remain the same as these are two different systems (at least for now), and anonymous participation will be activated with a checkbox in the component.

**How do we send notifications if we don’t have an email address?**
- To send notifications, the administrator will need to request an email address during participation.

**How do we manage if more than one action can be performed in a feature?**
- Each participation condition, at the time of its configuration, will have checkboxes to specify which actions the condition applies to.

**Is there a metaproposal for it?**
- Absolutely, here is the [link to the metaproposal](https://meta.decidim.org/processes/roadmap/f/122/proposals/17898).
