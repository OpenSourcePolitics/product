# Sequential voting interface a.k.a the "voting carousel"

## Challenge
The current voting process requires users to navigate through multiple proposals individually, leading to:
- Cognitive overload and user fatigue
- Reduced participation due to complex interaction patterns
- Potential bias towards proposals with catchy titles

## Solution
Implement an alternative, optional interface that presents proposals one at a time in a card-based sequential format.


https://github.com/user-attachments/assets/57aeaad1-8037-49f2-83c1-2fbe95b5416d


### Inspiration
Make.org's streamlined voting interface, which successfully implements a single-proposal-at-a-time presentation model.


https://github.com/user-attachments/assets/ccf08a2b-a1b0-4961-af32-dda3e4ae2ccd


### User stories

1. As a voter:
   - I want to see one proposal at a time to focus better on its content
   - I want to vote quickly without navigating between multiple pages
   - I want to see how many votes I have remaining (when voting limits apply)

2. As a platform administrator:
   - I want to enable/disable the sequential voting interface for specific processes
   - I want to maintain existing voting rules while offering a simpler interface

## Important constraints/considerations

1. Technical implementation:
   - Load proposals in batches for improved performance
   - Implement random selection of proposals within each batch
   - Maintain voting rule enforcement (min/max votes)
   - Provide clear voting progress indicators

2. User Experience:
   - Make the interface optional (users can choose between traditional and sequential views)
   - Display remaining votes counter when relevant
