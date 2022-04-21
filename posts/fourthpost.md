---
title: Considerations when Designing a Web Component
description: 
date: 2021-10-10
scheduled: 2021-10-10
tags: 
  - programming
  - web components
layout: layouts/post.njk
---
Before we make a web component we have to understand what we're making and plan out what we want to include in the functionality of the component.

### The Comp
Let's look to create a web component that displays a card. Our proposed design is to be able to make at least these three example cards with the same component.
![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/iluq8f2zam9oz3pl2vg6.png)


### The Breakdown
Looking at the image we can see each card has two sections, the header, and body content.

We should look at what elements are needed for each section:
##### Header
- SVG Icon
- Header Text
- Sub-header Text

##### Body
- Body Text

### The Approach and Possible Challenges
#### Approach
Based on our component breakdown we can see we'll need to make two sections that can be styled independently.

The header section will include our icon and two headers placed side-by-side. We can make the icon, header, and sub-header editable properties so that a user can change the content during implementation. We also need to make the background color of this section editable to set the banner color in our header.

The body section has text that needs to be easily editable. Rather than making a property, like with the headings, we could utilize a slot in our body to not only make the implementation process easier but also make the content more accessible.

#### Challenges
The biggest challenge I see is using different states to change the entire card's content. We can implement property states that will change all the text areas, icons, and colors based on a preset keyword. For example, looking at the design picture above, the third card could be a state named "question" which would dynamically change the background color of the header to blue and the icon to the question bubble. We can have several of these preset states that make it simpler for the person implementing our component.

### Previous Experience
Luckily, my team and I have had some experience making a web component in the past. Recently, we've made a [button](https://github.com/IST-402-Group-1/KMBtn) that plays short audio clips. In this button, we've touched on some aspects of dynamic states, such as a dark mode or when the button is disabled. We should be able to use the skills we learned previously and expand upon them to make this card component as reusable and reliable as possible.