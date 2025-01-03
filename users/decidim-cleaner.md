# Decidim Cleaner
The Decidim Cleaner module allows platform administrators to configure the automatic deletion of inactive user accounts and manage the administrative history. This tool helps organizations comply with GDPR requirements by providing mechanisms for handling user data in a responsible manner.

GitHub Repository: [Decidim Cleaner Module](https://github.com/OpenSourcePolitics/decidim-module-cleaner)

## Benefits of this module
- **GDPR Compliance:** By automating the deletion of inactive accounts, the module supports organizations in adhering to GDPR norms and recommendations for data retention and user privacy.
- **Clearer back-office:** The ability to delete administrative history over time ensures a cleaner and more organized back-office environment for administrators.

## Module usage overview
In the back office, in the Data cleaner tab of the Decidim global parameters, administrators can configure five key actions to manage user accounts and platform data effectively:
- Activate Inactive Account Deletion: Enable or disable the automatic deletion of inactive accounts.
- Configure Notification Email: Configure the sending of an inactivity warning email to inform inactive users about the upcoming deletion of their accounts and define the period of inactivity required before sending a notification email to users.
- Schedule Account Deletion: Specify the time period after the warning email during which accounts will be deleted if users do not re-login.
- Activate Administration History Deletion: Enable the automatic deletion of administrative history. 
- Schedule Admin History Deletion: Specify the time period after which the admin logs are deleted. 

## User stories
### Managing inactive users
- As an administrator, I want to enable or disable the option for deleting inactive accounts at any time from the back-office.
- As an administrator, I want to configure the sending of an email to inactive users informing them about the future deletion of their accounts, and I want to define the required inactivity duration.
- As an administrator, I want to define the time period after sending the notification email during which inactive accounts will be deleted if users do not re-login.
- As a user, I want to receive a notification email informing me of the upcoming deletion of my account due to inactivity.
- As a user, if I re-login to the platform after receiving the notification email, my account should not be deleted after the defined period has passed.
- As a user, if my account has been deleted due to inactivity, I should not be able to log back into the platform with my credentials.

### Managing administration history
- As an administrator, I want to configure the duration after which the admin logs is automatically deleted from the back-office. 
- As an administrator, once the administration history is deleted, I should no longer be able to view it in the platform's admin logs.