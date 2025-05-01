## Recap of the current situation

In Decidim, **private spaces** are used to restrict participation to a specific group of people. When creating or editing a *participatory process* or *assembly*, you can mark it as a **Private space** by checking the corresponding box. Only participants who are explicitly added to the space will be able to access and interact with its content.

To invite **private participants**, a **“Private participants”** section appears in the left-hand navigation of the admin panel for that space. From there, administrators can:

- **Manually add** new private participants by entering their name and email.
- **Bulk import** participants using a **CSV file** with two columns (email, name), no headers, and comma-separated values.

**Then:**

- If the email is already linked to an account on the platform, access is granted immediately, and no email is sent.
- If the participant does **not** already have an account:
  - An **invitation email** is sent with a link to join.
  - The participant clicks the link and completes registration by choosing a nickname, setting a password, and accepting the Terms of Service.

Admins can see a list of private participants, including:

- Name and email
- Whether the invitation was sent or accepted, and when

These are the actions available to admins:

- **Resend invitation** if it was not accepted
- **Delete invitation** to revoke access

---

## Problems with the current situation

- Email invitations often go to spam
- People who already have accounts don’t receive an email and often don’t realize they now have access to a private space
- CSV files are often incorrectly formatted and rejected – even experienced consultants struggle with the process

---

## Ideas for solutions

**Send an email to people invited to a private space, even if they already have an account**

- Let them know they’ve been invited and include a direct link to the space
- Allow admins to customize the invitation message

**Make it possible to create an invite link that anyone can use to join the private space**

- Admins can choose to require approval for people who join via the link
- Admins can choose to make the link expire after a certain amount of time

_Inspiration for the UX:_

- WhatsApp  
- Google Docs  
- Docs

**For transparent private spaces, let people ask to join and admins approve them**

_Inspiration for the UX:_

- Facebook groups

