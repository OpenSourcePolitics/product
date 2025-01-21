# Feature proposal: "Other proposals suggestions"
Metaproposal link : https://meta.decidim.org/processes/roadmap/f/122/proposals/17809

## Problem 
When users view a proposal, there's a missed opportunity for engagement by not showing them other relevant proposals. Similar features are common across platforms like YouTube's video suggestions or related articles in media sites. Implementing this feature ethically and in a balanced way could significantly improve user experience, especially since the drawer concept has been discontinued.

In other words, at the moment :
- After reading a proposal, users face a "dead end" - they must manually navigate back to listings or search
- Time spent per session is likely reduced due to friction in content discovery
- Manual navigation increases cognitive load, potentially reducing return visits
- Lack of suggestion features puts Decidim behind modern platform UX expectations
- Current navigation requires multiple clicks through category/tag pages to find related content


## Proposed solution
Add a dedicated "Other Proposals" section in the right sidebar and display 3-5 related proposals with:
- Proposal title (truncated if needed)
- Support count and commenting status

![image](https://github.com/user-attachments/assets/6fa9e3e5-bd47-4beb-8483-63224356ab2f)

On mobile, proposal suggestions should go below the comments section. 


The administrators should be able to choose based on what factors the proposals should be displayed in the configuration of the proposals component : 
- Location (using geocoding or scope)
- Category
- Random selection (refreshed at each visit of a proposal)
- Most recent proposals

If the administrator chooses to prioritize based on location or category, if there are not enough proposals based on the criteria, the "other suggestions" algorithm should fallback to "random".
