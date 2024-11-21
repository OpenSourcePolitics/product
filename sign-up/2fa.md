# Two-factor authentication (2FA) spec

Implement 2FA for admin dashboard access in Decidim, requiring verification only when accessing admin features.

## Core requirements

### Authentication flow
1. Users login normally with email/password/SSO
2. 2FA triggers only when accessing admin dashboard
3. Regular users bypass 2FA completely

```mermaid
graph TD
    A[User login] --> B{Is admin?}
    B -->|No| C[Access regular dashboard]
    B -->|Yes| D[Try access admin dashboard]
    D --> E[Request 2FA]
    E --> F[Send code via Email/SMS/Webauthn]
    F --> G[User enters code]
    G --> H{Code valid?}
    H -->|Yes| I[Access admin dashboard]
    H -->|No| E
```

### 2FA methods
- Email verification code
- SMS verification code  
- Webauthn

### Configuration options
Configure via either:
- `/system` page 
- Admin panel settings section

Example of how it could look like in the admin panel:
![screely-1732194638130](https://github.com/user-attachments/assets/ed0192e7-56e7-40d8-8602-5a9c252854a5)


## Implementation notes
- Maintain existing authentication for regular users
- Add 2FA layer only for admin dashboard access
- Do as the whole 2FA process in a popup
- Support multiple 2FA methods simultaneously
- Reuse the same email structure as friendly-signup
![screely-1732195015627](https://github.com/user-attachments/assets/fecb5a85-5a82-4e05-b136-bc22517dd779)
- Be compatible with all SMS providers we have already developed for:
  - gem "decidim-smsauth", github: "OpenSourcePolitics/decidim-module-ptp", branch: "feature/0.26/zip-code-voting"
  - gem "decidim-sms-twilio", github: "OpenSourcePolitics/decidim-module-ptp", branch: "feature/0.26/zip-code-voting"
  - https://github.com/OpenSourcePolitics/decidim-app/pull/519
  - https://github.com/OpenSourcePolitics/decidim-app/pull/605

## Security considerations
- Secure token storage
- Rate limiting for verification attempts
- Session timeout rules for verified states

