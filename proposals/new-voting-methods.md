# Voting in favour or against proposals in Decidim  

Decidim currently offers basic proposal voting functionality that only allows positive votes. While this approach promotes constructive engagement and support, it limits users' ability to express their full range of preferences and opinions.

We propose implementing bi-directional voting (positive and negative) for proposals in Decidim. This enhancement would:
1. Enable comprehensive opinion expression
2. Help identify controversial proposals
3. Present a more accurate representation of community sentiment
  

## **Current solution : Decidim Awesome**

The Decidim Awesome module currently provides weighted voting functionality as an extension.

**Strengths:**
- Production-ready implementation
- Configurable voting weights

**Limitations:**  
- Stability concerns
- Non-native user experience
- Interface refinement needed

## **Core implementation proposal** 

### **Rationale for core integration**
- Secured European Commission funding requires core implementation
- Strong community consensus supporting this feature
- Opportunity to enhance core functionality
- Enables improved integration and administrative configuration

### **How we would suggest integrating it in the core**

Two options: 

### Option 1: like button replacement
An elegant integration that would replace the current like button with a bi-directional voting mechanism.
![screely-1736846055841](https://github.com/user-attachments/assets/72b9f80e-9d29-4b87-95c9-eae81d00d938)


  

### Option 2: current vote button position  
Implementation at the existing vote button location.
![screely-1736845878389](https://github.com/user-attachments/assets/a535eec9-bfe1-4599-86eb-e510d0cf5c84)


The current coexistence of likes and votes creates user confusion, even among Decidim administrators and consultants.

**Proposed Solution:**
Transform the endorsement system into a configurable voting type, allowing administrators to choose between:

- Simple endorsements
- Positive-only voting
- Bi-directional voting (positive and negative)

This approach eliminates redundancy while maintaining flexibility in how communities can engage with proposals.


### **To go even further - rethinking the voting experience with a voting carousel**  

You can see this new voting system integrating in another product specification we are suggesting - [the voting carousel](https://github.com/OpenSourcePolitics/product/blob/main/proposals/voting-carousel.md). 


