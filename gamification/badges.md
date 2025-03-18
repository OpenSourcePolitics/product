# Badges on Decidim

## Challenge
The current badge system is quite limited, offering only generic badges that cannot be modified, added, or removed by the organization. More personalized and meaningful badges could materialize the expected positive outcomes of gamification of participation.

## Solution
An enhanced badge system where we can create new badges, modify existing ones, and activate or deactivate them as needed. This would make the experience more rewarding and tailored to the community.
The admin could create badges and define at what conditions they are assigned. Potentially some badges could be specific to some participatory spaces or components.


https://github.com/user-attachments/assets/40ac50c8-593d-4311-9205-6b1c977fee5b

### Inspiration
- Stack Overflow's badge system - Organizes badges into categories (Bronze, Silver, Gold) based on difficulty and offers clear paths to achievement

  ![image](https://github.com/user-attachments/assets/00ed072e-f2bb-4c2b-8e9c-3481b62bdeaf)
- GitHub's achievement system - Badges for specific contributions and milestones that celebrate user activity
  ![image](https://github.com/user-attachments/assets/c33085f8-f60e-4559-80ba-5f03c69f5d69)
- [Open Badges standard](https://openbadges.org/) - Would be interesting to try making it interoperable with the standard

### User stories

As an administrator:
1. I want to select which badges should be available from a pre-defined set of badges (division into active and inactive badges, same as for components).
2. I want to create custom badges with unique names, descriptions, and icons so I can tailor recognition to my community's goals.
3. I want to set specific conditions for badge achievement (e.g., number of proposals created, comments posted, votes cast) so badges are awarded automatically. Participatory space conditions should also be available (e.g., only give this badge for proposals created in the participatory budget)

As a participant:
1. I want to see which badges I've earned and display them on my public profile
2. I want to receive notifications when I receive a new badge

### Developing this solution in iterations

#### First iteration

The first iteration would be especially focused on the first administrator user story : as an administrator I want to select which badges should be available from a pre-defined set of badges (division into active and inactive badges, same as for components). This page would be available as on of the settings tabs in the back office 

![Screenshot 2025-03-18 at 08 34 38](https://github.com/user-attachments/assets/1d51ea87-98a6-4986-a223-d1d7834c910f)


In order to have some possibility of customization, these badges could be described in JSON, YML or any other data structure inside the config of the application so as to give the possibility for technical administrators to modify them. 

#### Second iteration

The major change with the second iteration should be the added flexibility for the administrator, where in order to create additional badges, they could do that from the back office.
